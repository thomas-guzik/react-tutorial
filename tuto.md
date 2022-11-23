# React education

# Installer npm

# Créer votre première application

`npx create-react-app my-app --template typescript`

# Faites votre premier composant enfant

Créer un nouveau fichier `.tsx`, tsx pour typescript extension

```jsx
function Parent() => {
    return <p>
    J'ai 3 enfants
    <Enfant />
    <Enfant />
    <Enfant />
    </p>
}
```

```jsx
function Enfant() => {
    return <e>I'm born</e>
}
```


## Donner à votre enfant des informations

```jsx
type Enfant {
    nom: string
}
function Enfant() => {
    return <p>Je m'appelle {nom}</p>
}
```

Donner un age à vos enfants dans une deuxième balise.

Aide : Pour avoir plusieurs balises, vous pouvez utiliser `<></>`

## Votre enfant veut faire preuve d'autonomie, il veut savoir compter

```jsx
type Enfant {
    nom: string
}
function Enfant() => {
    const [counter, setCounter] = useState<number>(0);

    return <>
    <p>Je m'appelle {nom}</p>
    <bouton onClick={() => setCounter(counter + 1)}</bouton>
    </>
}
```

Il veut maintenant savoir compter à l'envers

## Votre enfant veut vous donner des informations

```jsx
function Parent() => {
    const [whatSayYourChild, setWhatSayYourChild] = useState<string>("");

    return <p>
    Mon enfant dit {whatSayYourChild}
    <Enfant onSay={(s:string) => {setWhatSayYourChild(s)}}/>

    </p>
}
```

```jsx
function Enfant() => {
    return <input type="text" onChange={(e: ChangeEvent<HTMLInputElement>) => {return e.target.value;}}/>
}
```

Afficher une liste des messages de vos enfants [{"enfant1":"Hello"},{"enfant2":"Hey"},{"enfant1":"Salut"},{"enfant1":"Yo"}],


## Calcul au sein de la page

Faire la multiplication de 2 inputs

# Communiquer avec les api

Installer axios

`npm install axios`

Compléter le code à trou

```ts
const axelor_url = "https://project-apexenergies.axelor.com/";

 export default class AxelorAPI  {
    static cookie = "";
 
    static login() {
    
    }
 
    static read_all() {
        return {};
    }

    static read(model: string,id: string | number | undefined) {
        return axios.get(`${axelor_url}ws/rest/{model}/{idd}`);
    }
    
    static create() {
        return {};
    }
    
    static update(model: string,id: string | number | undefined) {
        return {};
    }

    static delete(calc: Calc) {
        return {};
    }

    static export(calc: Calc) {
        return {};
    }
}

## Appeller votre api au chargement de la page

## Externaliser le useEffect


# CORS error avec le back-end


# Hooks + compliqué

# React bonne pratique
- Décomposer les composants graphiques avec seulement css
- Découper le code. API, VUE, MODEL, FONCTION
- Une vue = une LISTE de composant
- Une fonction = un ensemble de fonction permattant de réaliser une seule chose ou une chose qui se ressemble. PAS DE FICHIER AVEC PLUSIEURS FONCTIONNALITE A L'INTERIEUR (CRUD et des calculs par ex). Un fichier par user story. Tant pis si le fichier ne fait que 5 lignes.
- Un model = définit les champs, important pour la compréhension général du code



