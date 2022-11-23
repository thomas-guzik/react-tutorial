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
    return <input type="text" onChange={(s) => {}}/>
}
```

# React bonne pratique
- On décompose 
