

## Evaluation of Multi-Speaker Voice Cloning Model (ConquiAPI)

1\. ConquiApi allows us to convert the text into three distinct languages i.e. English(en), French(fr),and Portuguese(pt-br) with six different speakers.

```
Available Languages:
['en', 'fr-fr', 'pt-br']
Available Speakers:
['female-en-5', 'female-en-5\n', 'female-pt-4\n', 'male-en-2', 'male-en-2\n', 'male-pt-3\n']
```

2\. For evaluating the conversion we have computed real time factor and processing time of multiple speakers on same text with different languages.

```
Input Text
English    ="This is a test! This is also a test!!"
French     ="C'est un test! C'est aussi un essai !!"
Portuguese ="Isto é um teste! Isso também é um teste!!"
```

#### Speaker 1

```
English
> Processing time: 2.4665820598602295
> Real-time factor: 0.5623762106384472
French
> Processing time: 1.0531597137451172
> Real-time factor: 0.3074021347767417
Portuguese
> Processing time: 1.302067518234253
> Real-time factor: 0.25185058379772784
```

#### Speaker 2
```
English
> Processing time: 1.039297342300415
> Real-time factor: 0.24500173085818364
French
> Processing time: 0.6900172233581543
> Real-time factor: 0.22924160244456954
Portuguese
> Processing time: 1.1344976425170898
> Real-time factor: 0.24272521234854294
```

#### Speaker3
```
English
> Processing time: 1.7226967811584473
> Real-time factor: 0.39420978973877513
French
> Processing time: 1.092313289642334
> Real-time factor: 0.34632634421126635
Portuguese
> Processing time: 1.6640985012054443
> Real-time factor: 0.37803237192309047
```

#### Speaker 4
```
English
> Processing time: 1.3879218101501465
> Real-time factor: 0.36893190062470665
French
> Processing time: 0.8564736843109131
> Real-time factor: 0.32417626204046673
Portuguese
> Processing time: 1.266613245010376
> Real-time factor: 0.31649506372073366
```

#### Speaker 5
```
English
> Processing time: 0.9403679370880127
> Real-time factor: 0.23497449702349144
French
> Processing time: 0.583432674407959
> Real-time factor: 0.2106255142267
Portuguese
> Processing time: 0.8663082122802734
> Real-time factor: 0.23325476905769343
```

#### Speaker 6
```
English
> Processing time: 0.9683349132537842
> Real-time factor: 0.23909504030957635
French
> Processing time: 0.5947566032409668
> Real-time factor: 0.2134804749608639
Portuguese
> Processing time: 1.0917878150939941
> Real-time factor: 0.24101276271390598
```

3)-Evaluation of audio generated using a single speaker model(Tacatron2-DDC)

```
Input text="Ich bin eine Testnachricht."
> Processing time: 4.527503728866577
> Real-time factor: 2.3625392186081986
```

4)-Evaluation of Voice Cloning Model, for evaluating the cloned voice with the original one what we did we first extract the embeddings from the cloned voice and original voice with TDNN model using SpeechBrain that trains on Voxceleb1+Voxceleb2 training data and after that, we computed the score by comparing the embeddings using cosine similarity and as our score get closer to 1 implies our cloned voice is more similar to original one.


Voice Cloning into distinct languages:-

```
Input Text
"This is voice cloning."
"C'est le clonage de la voix."
"Isso é clonagem de voz."
```

1\. Score for sample voice 1

English
```
> Processing time: 1.626028060913086
> Real-time factor: 0.7103661253442927
> Cosine Similarity Score: 0.8349373
```

French
```
> Processing time: 0.17424368858337402
> Real-time factor: 0.09547599374431454
> Cosine Similarity Score: 0.80558157
```
Portuguese
```
> Processing time: 0.18082308769226074
> Real-time factor: 0.06106824981163821
> Cosine Similarity Score: 0.85979676
```

2\. Score for sample voice 2

English
```
> Processing time: 0.2636582851409912
> Real-time factor: 0.14704868106022934
> Cosine Similarity Score: 0.74992824
```

French
```
> Processing time: 0.17833900451660156
> Real-time factor: 0.11139225766183733
> Cosine Similarity Score: 0.7625568
```

Portuguese
```
> Processing time: 0.17746376991271973
> Real-time factor: 0.06560582991228085
> Cosine Similarity Score: 0.8049873
```


### Voice Cloning Using Tactron2-DDC

```Input Text="Wie sage ich auf Italienisch, dass ich dich liebe?"```

1\. Score for sample voice 1
```
> Processing time: 5.537316560745239
> Real-time factor: 1.8130468960030965
> Cosine Similarity Score: 0.8399157
```

2\. Score for sample voice 2
```
> Processing time: 3.7568535804748535
> Real-time factor: 1.2300816917538389
> Cosine Similarity Score: 0.9216579
```


### Time in loading model with or without GPU

1\. Tacotron-2 DDC(single speaker model)
```
GPU(True)=64.4503824710846
GPU(False)=84.92006945610046 
```    

2\. Multilingual Model(allows voice cloning to multiple language)

```
GPU(True)=18.482767343521118
GPU(False)=21.874202251434326
```

3\. FreeVC24(Voice cloning model)
```
GPU(True)=79.87649631500244
GPU(False)=80.75335383415222
```
