[MusicVAE](https://g.co/magenta/music-vae) learns a latent space of musical sequences

This kiko-vae developed basd on autoencoder and can generate full drum kit sequence from kick-only sequence

## Training Your Own MusicVAE
If you'd like to train a model on your own data, you will first need to set up
your [Magenta environment](/README.md). Next, convert a collection of MIDI files
into NoteSequences following the instructions in
[Building your Dataset](/magenta/scripts/README.md). You can then choose one of
the pre-defined Configurations in [configs.py](configs.py) or define your own.
Finally, you must execute the [training script](train.py). Below is an example
command, training the `cat-mel_2bar_small` configuration and assuming your
examples are stored at `/tmp/music_vae/mel_train_examples.tfrecord`.

```
music_vae_train \
--config=cat-mel_2bar_small \
--run_dir=/tmp/music_vae/ \
--mode=train \
--examples_path=/tmp/music_vae/mel_train_examples.tfrecord
```

You will likely need to adjust some of the hyperparamters with the `--hparams`
flag

```
--hparams=batch_size=32,learning_rate=0.0005
```

## For javascript examples using magenta.js, visit https://github.com/tensorflow/magenta-js