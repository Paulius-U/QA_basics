# QA_basics


# Užduotys kokybės metrikos:

Pasirinkti tyrimui programų sistemą ir prieigą prie jos išeities tekstų. Pagrįsti jos pasirinkimą

Metrikų skaičiavimui taikyti pasirinktą įrankį. Pagrįsti jo pasirinkimą

Išmatuoti dydžio metrikas: LOC, CLOC, NCLOC ir pan. Mokėti jas pakomentuoti gautas vertes

Išmatuoti sudėtingumo metriką: Halstead‘o metrikas: žodynas, ilgis, apimtis, sunkumas, pastangos, PS gylis, klaidų skaičius. Mokėti jas pakomentuoti gautas vertes.

Išmatuoti sudėtingumo metrikas (cyclomatic and cognitive complexity):

a.       Apskaičiuoti ir įvertinti McCabe metrikas klasės/failo;

b.       Apskaičiuoti ir įvertinti pasirinktų 3-5 metodų/funkcijų ciklomatinį ir kongnityvinį sudėtingumo vertes. Parinkti nevienodas vertes turinčius metodus

c.       Mokėti pakomentuoti pasirinkto metodo kognityvinį ir ciklomatinį sudėtingumą. Kiek reikėtų testinių atvejų šiems metodams padengti testais?

d.       Pasiūlyti praktinius būdus kaip sumažinti sudėtingumo vertę.

Apskaičiuoti/pateikti programos kodo prižiūrimumo indeksą. Mokėti pakomentuoti gautą vertę.

Išmatuoti pasirinktinai OO/skriptinio sudėtingumo metrikas: WMC, CBO, RFC, NOC, DIT. Būtina Cohesion ir Coupling.

Pateikti bendrąsias išvadas apie PS kodo kokybę, jos prižiūrimumą, kodo klaidų tikimybę jį atnaujinant, perdarant. Prognozuoti defektų jautrumo, defektų santykis ir kitas metrikas.



# Programų sistemos kodo kokybės metrikų skaičiavimas ir įvertinimas (Paulius Ulevičius)

 

Dydžio metrikos
LOC - lines of code,

CLOC - comment lines of code,

NCLOC - non-comment lines of code.

Summary
Date : 2023-10-22 22:15:18

Directory d:\QA\calorie-calculator-python-code\Fityfeed

Total : 32 files, 1027 codes, 142 comments, 171 blanks, all 1340 lines

Languages
language

files

code

comment

blank

total

HTML

10

601

7

65

673

Python

22

426

135

106

667

Directories
path

files

code

comment

blank

total

.

32

1,027

142

171

1,340

. (Files)

11

259

125

44

428

migrations

11

167

10

62

239

templates

10

601

7

65

673

![image](https://github.com/Paulius-U/QA_basics/assets/75576100/c746a389-4f3d-4482-8d68-0f2de7d39aae)

VS code Counter rezultatai
Kodo funkcija - registerPage / loginPage


@unauthorized_user
def registerPage(request):
    form=createUserForm()
    if request.method=='POST':
        form=createUserForm(request.POST)
        if form.is_valid():
            user=form.save()
            username=form.cleaned_data.get('username')
            group=Group.objects.get(name='user')
            user.groups.add(group)
            email=form.cleaned_data.get('email')
            Customer.objects.create(user=user, name=username,email=email)
            messages.success(request,'Account created for '+username)
            return redirect('login')
    context={'form':form}
    return render(request,'register.html',context)

@unauthorized_user
def loginPage(request):
    if request.method=='POST':
        username=request.POST.get('username')
        password=request.POST.get('password')
        user=authenticate(request,username=username,password=password)
        if user is not None:
            login(request,user)
            return redirect('home')
        else:
            messages.info(request,'username or password is invalid')
    return render(request,'login.html')
 

Halstead‘o metrikos
Operatoriai:

= (16)

== (2)

if (4)

return (4)

. (23)

() (22)

+ (1)

{} (1)

: (8)

def (2)

Operandai:

@unauthorized_user (2)

registerPage (1)

request (13)

form (10)

createUserForm (2)

POST (5)

is_valid (1)

user (11)

username (9)

group (3)

Group (1)

objects (2)

get (5)

email (4)

Customer (1)

create (1)

'Account created for ' (1)

context (2)

render (2)

'register.html' (1)

loginPage (1)

password (5)

authenticate (1)

login (2)

'home' (1)

messages (2)

'username or password is invalid' (1)

'login.html' (1)

N1 = 10 
N2 = 28
n1 = 83
n2 = 91

Programos ilgis (N): N = N1 + N2 = 10 + 28 = 38

Programos žodynas (n): n = n1 + n2 = 83 + 91 = 174

Programos apimtis (V): V = N * log2(n) = 38 * log2(174) ≈ 38 * 7.459 = 283.142

Sunkumas (D): D = (N1 / 2) * (N2 / n1) = (10 / 2) * (28 / 83) ≈ 1.205

Pastangos (E): E = D * V ≈ 1.205 * 283.142 ≈ 341.194

Galimų klaidų skaičius (B): B ≈ (341.194 ^ (2/3)) / 3000 ≈ 0.175

 

McCabe metrikos
McCabe metrikos apskaičiuojama su kodu ir naudojant Catalyze extension per VS Code.

![image](https://github.com/Paulius-U/QA_basics/assets/75576100/68b0258b-74de-42c6-995b-c795e5ec98c9)

code:
import radon
from radon.complexity import cc_visit, cc_rank

def calculate_cyclomatic_complexity(code):
    try:
        cc_results = cc_visit(code)
        complexity = cc_results[-1].complexity
        return complexity
    except Exception as e:
        return str(e)

sample_code = """
"""

complexity = calculate_cyclomatic_complexity(sample_code)
print(f'Cyclomatic Complexity: {complexity}')

Cyclomatic Complexity: 3

Eilučių kiekis (LOC) = 29

Cognitive complexity: 4 

Prižiūrimumo indeksas
Naudotas skaičiavimo variantas MI4:

MI4 = 171 - 5.2 * ln(HV) - 0.23 * CC - 16.2 * ln(LOC)

MI ≈ 171 - 5.2 * ln(283.142) - 0.23 * 3 - 16.2 * ln(174)

MI ≈ 171 - 5.2 * 5.645 - 0.69 - 16.2 * 5.159

MI ≈ 171 - 29.294 - 0.69 - 83.482

MI ≈ 171 - 29.294 - 0.69 - 83.482 ≈ 57.534

Kodo funkcija - allowed_users 


def allowed_users(allowed_roles=[]):
    def decorator(view_func): 
        def wrapper_func(request,*args,**kwargs):
            group=None
            if request.user.groups.exists():
                group=request.user.groups.all()[0].name
            if group in allowed_roles:
                return view_func(request,*args,**kwargs)
            else:
                return HttpResponse("<h1>You are not allowed to access this page</h1>")
        return wrapper_func
    return decorator
Halstead‘o metrikos
Operatoriai:

def (3)

() (7)

if (2)

return (4) 

= (3)

. (7)

* (2)

** (2)

[] (2)

Operandai:

allowed_roles (2)

view_func (2)

wrapper_func (2)

request (4)

args (4)

kwargs (2)

group (5)

HttpResponse (1)

 

N1 = 9 
N2 = 8
n1 = 32
n2 = 22

Programos ilgis (N): N = N1 + N2 = 9 + 8 = 17 

Programos žodynas (n): n = n1 + n2 = 32 + 22 = 54

Programos apimtis (V): V = N * log2(n) = 17 * log2(54) ≈ 17 * 5.75488750216 ≈ 97.938

Sunkumas (D): D = (N1 / 2) * (N2 / n1) = (9 / 2) * (8 / 32) = 1.125

Pastangos (E): E = D * V ≈ 1.125 * 97.938 ≈ 110.117

Galimų klaidų skaičius (B): B ≈ (E ^ (2/3)) / 3000 ≈ (110.117 ^ (2/3)) / 3000 ≈ 0.127

 

Cyclomatic Complexity: 1

Eilučių kiekis (LOC) = 12

Cognitive complexity: 5 

Prižiūrimumo indeksas
 MI4 = 171 - 5.2 * ln(HV) - 0.23 * CC - 16.2 * ln(LOC)

MI ≈ 171 - 5.2 * ln(97.938) - 0.23 * 1 - 16.2 * ln(12)

MI ≈ 171 - 5.2 * 4.586 - 0.23 - 16.2 * 2.4849

MI ≈ 171 - 23.8712 - 0.23 - 40.33438

MI ≈ 171 - 23.8712 - 0.23 - 40.33438 ≈ 106.564

Kodo funkcija - Customer
 



class Customer(models.Model):
    user = models.OneToOneField(User, null=True, on_delete=models.CASCADE)
    name=models.CharField(max_length=200,null=True)
    email=models.CharField(max_length=200,null=True)
    date_created=models.DateTimeField(auto_now_add=True,null=True)
    
    def __str__(self):
        return str(self.name)

class Category(models.Model):
    options=(
        ('breakfast','breakfast'),
        ('lunch','lunch'),
        ('dinner','dinner'),
        ('snacks','snacks'),
    )
    name=models.CharField(max_length=50,choices=options)
    def __str__(self):
        return self.name
Halstead‘o metrikos
Operatoriai:

class - 2 

= - 4 

models - 6 

. (taškas) - 6 

OneToOneField - 1 

null - 4 

on_delete - 2 

CharField - 2 

max_length - 2 

DateTimeField - 1 

auto_now_add - 1 

def - 2 

return - 2 

Category - 2 

options - 1 

'breakfast', 'lunch', 'dinner', 'snacks'

Operandai:

Customer - 1 kartas 

models - 2 kartai 

User - 1 kartas 

null - 4 kartai 

name - 2 kartai 

email - 2 kartai 

date_created - 2 kartai 

Category - 1 kartas 

options - 1 kartas 

 

N1 = 19 
N2 = 9
n1 = 42
n2 = 16

 

 

Programos ilgis (N): N = N1 + N2 = 19 + 9 = 28 

Programos žodynas (n): n = n1 + n2 = 42 + 16 = 58

Programos apimtis (V): V = N * log2(n) = 28 * log2(58) ≈ 28 * 5.85802469135 ≈ 163.904691358

Sunkumas (D): D = (N1 / 2) * (N2 / n1) = (19 / 2) * (9 / 42) ≈ 2.25

Pastangos (E): E = D * V ≈ 2.25 * 163.904691358 ≈ 368.786555555

Galimų klaidų skaičius (B): B ≈ (E ^ (2/3)) / 3000 ≈ (368.786555555 ^ (2/3)) / 3000 ≈ 0.158

 

Cyclomatic Complexity: 1

Eilučių kiekis (LOC) = 19

Cognitive complexity: 4 

 

Prižiūrimumo indeksas
MI4 = 171 - 5.2 * ln(HV) - 0.23 * CC - 16.2 * ln(LOC)

MI ≈ 171 - 5.2 * ln(163.904691358) - 0.23 * 1 - 16.2 * ln(19)

MI ≈ 171 - 5.2 * 5.1049354438 - 0.23 - 16.2 * 2.9444389792

MI ≈ 171 - 26.5327902396 - 0.23 - 47.7870531554

MI ≈ 171 - 26.5327902396 - 0.23 - 47.7870531554 ≈ 96.449156605

 

OO/skriptinio sudėtingumo metrikas: WMC, CBO, RFC, NOC, DIT.
Sudėtingumo metrikoms (WMC, CBO, RFC, NOC, DIT) skaičiuoti pasinaudojau IntelliJ IDEA plugin Metricreaderd.

 

Kadangi mūsų projektas nėra OOP programa todėl buvo gauti rezultatai su 100 %.

![image](https://github.com/Paulius-U/QA_basics/assets/75576100/85db0d8d-ebd1-474b-ba51-4ea89c0f6d80)

Calory_calcolator projekt sudėtingumo metrika
Todėl kad gautume naujus rezultatus kurie nebūtų 100 % buvo naudojama visai naujas projektas. Naujas projektas yra minesweeper. 

Nauji rezultatai buvo gauti tokie:

![image](https://github.com/Paulius-U/QA_basics/assets/75576100/dd84dd24-f39a-4f6b-ad0f-38c80d75e70a)

Minesweeper projekto sudėtingumo metrika
AHF (Aukšto lygio modulių abstraktumas) - 75,56 %: 

Ši metrika vertina, kiek programos modulių yra abstraktūs arba aukšto lygio. 75,56 % reiškia, kad dauguma modulių yra abstraktūs, kas gali būti gera praktika, nes abstraktūs moduliai gali būti lengviau panaudojami kitose dalyse programos.

AIF (Abstraktumo nestabilumo koeficientas) - 0 %: 

Ši metrika vertina, kiek abstraktūs moduliai yra stabilūs. 0 % rodo, kad abstraktūs moduliai yra labai stabilūs, tai gali būti laikoma geru rezultatu, nes stabilūs moduliai yra mažiau linkę į pokyčius.

CF (Susiejimo koeficientas) - 80 %: 

Ši metrika rodo, kiek klasių programoje yra susijusios su kitomis klasėmis. 80 % rodo gana didelį susiejimą tarp klasių. Tai gali padidinti programos sudėtingumą ir priklausomybę tarp klasių.

MHF (Aukšto lygio modulių išlaikymo indeksas) - 5,71 %: 

Ši metrika nurodo, kiek aukšto lygio modulių yra lengvai palaikomi ir išlaikomi. 5,71 % rodo, kad tik nedidelė dalis aukšto lygio modulių yra lengvai palaikomi. Tai gali reikšti, kad palaikymas ir pataisymai gali būti sunkūs.

MIF (Maintainability Index Instability Factor) - 0 %: 

Ši metrika taip pat susijusi su palaikymo indeksu ir nestabilumu. 0 % rodo, kad programos išlaikymo aspektas yra labai stabilus.

PF (Perkeliamumo koeficientas) - 100 %: 

Ši metrika rodo, kad programa yra labai lengvai perkeliama, t.y., ji yra nepriklausoma nuo konkrečios platformos ar aplinkos.
