@box[bg-blue](MAYBE IN ELM!)

@snap[south-east span-10]
![Logo](assets/img/luminara_logo.png)
@snapend

---

## Hello Everyone


![IMAGE](assets/img/hello_luminara.gif)

@snap[south-east span-10]
![Logo](assets/img/luminara_logo.png)
@snapend

---?color=linear-gradient(180deg, white 75%, black 25%)
@title[Customize Slide Layout]

@snap[north-west span-10]
## Why Maybe?
@snapend

@snap[south span-100 text-white]
Uncertainty is present everywhere in the world and consequently in our code because we try to model the world and the processes that happen there.
@snapend

---?color=linear-gradient(90deg, #5384AD 65%, white 35%)
@title[Add A Little Imagination]

@snap[north-west h4-white]
#### How Elm Handles/solves the uncertainty problem...
@snapend


@snap[west span-50]
@ul[list-spaced-bullets text-white text-09]
- the uncertainty problem present in other languages like JS where they by default “TRUST NO ONE”, elm prefers to “TRUST EVERYONE” by default
- (ie unless you have explicitly told me that this value is optional I am going to assume and going to enforce that this value be present)
@ulend
@snapend

---?color=linear-gradient(90deg, #5384AD 65%, white 35%)
@title[Add A Little Imagination]

@snap[north-west h4-white]
#### Some remarks on using Maybe in Elm
@snapend

@snap[west span-50]
@ul[list-spaced-bullets text-white text-09]
- Any value can be missing at any time (This is fixed just by using elm, it is free)
- **Maybe** type is just as Viral as *Null* is present in JS and other languages
@ulend
@snapend

---?color=linear-gradient(90deg, #5384AD 65%, white 35%)
@title[Add A Little Imagination]

@snap[north-west h4-white]
#### Some _Maybe_ functions in Elm
@snapend

@snap[west span-50]
@ul[list-spaced-bullets text-white text-09]
- Any value can be missing at any time (This is fixed just by using elm, it is free)
- **Maybe** type is just as Viral as *Null* is present in JS and other languages
@ulend
@snapend


---

@snap[north-east span-100 text-black text-06]
Let's talk in CODE!
@snapend

```elm zoom-18
import Html exposing (..)

type alias Location = {
    lat: Float,
    lon: Float,
    favorite; Maybe Bool
}

isFavorite: Bool -> String
isFavorite favoriteOrNot =
    if favoriteOrNot then
        "Yes, my favorite"
    else 
        "Nope, not my favorite"

isFavorite2: Bool -> Maybe String
isFavorite2 favoriteOrNot =
    if favoriteOrNot then
        Just "Yes, it is my favorite"
    else 
        Just "Nope, it is not my favorite location"

combine: Maybe Bool -> Maybe Bool -> Maybe Bool
combine first second = 
    Maybe.map2 (||) first second

process: Location -> String
process location =
    Maybe.withDefault "I don't have an option" (Maybe.map isfavorite location.favorite)

process2: Location -> String
process2 location =
    case location.favorite of
        Just value ->
            case value of
                True -> "We got a true..."
                False -> "We got a false"
        _ -> "We got nothing" -- Here we can also use a "Nothing"


main =
    let
        location = Location 84.12 115.14 (Just False)
    in
        text (Debug.toString (process2 location))
            
```

---?image=assets/img/presenter.jpg

@snap[north span-100 h2-white]
## Now It's Your Turn
@snapend

@snap[south span-100 text-06]
[Click here to jump straight into the interactive feature guides in the GitPitch Docs @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend
