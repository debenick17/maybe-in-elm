@box[bg-blue](MAYBE IN ELM!)

@snap[south-east span-10]
![Logo](assets/img/luminara_logo.png)
@snapend

---

## Hello Everyone


![IMAGE](assets/img/hello_luminara.gif)

---?color=linear-gradient(180deg, white 75%, black 25%)
@title[Customize Slide Layout]

@snap[west span-50]
## Customize the Layout
@snapend

@snap[east span-50]
![IMAGE](assets/img/presentation.png)
@snapend

@snap[south span-100 text-white]
Snap Layouts let you create custom slide designs directly within your markdown.
@snapend

---?color=linear-gradient(90deg, #5384AD 65%, white 35%)
@title[Add A Little Imagination]

@snap[north-west h4-white]
#### And start presenting...
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-white text-09]
- You will be amazed
- What you can achieve
- *With a little imagination...*
- And **GitPitch Markdown**
@ulend
@snapend

@snap[east span-45]
@img[shadow](assets/img/conference.png)
@snapend

---

@snap[north-east span-100 text-pink text-06]
Let your code do the talking!
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

@snap[south span-100 text-gray text-08]
@[1-5](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
@[6,7, zoom-13](Using GitPitch live code presenting with optional annotations.)
@[8-9, zoom-12](This means no more switching between your slide deck and IDE on stage.)
@snapend


---?image=assets/img/presenter.jpg

@snap[north span-100 h2-white]
## Now It's Your Turn
@snapend

@snap[south span-100 text-06]
[Click here to jump straight into the interactive feature guides in the GitPitch Docs @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend
