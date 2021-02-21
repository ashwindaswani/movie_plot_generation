# Movie Plot Generator
Finetuning GPT2 model in pytorch to generate synopsis of the movie from the given title

## Usage 

- ### Training 
>  !python "/content/drive/My Drive/story-writer/finetuning.py" \
    --output_dir="/content/drive/My Drive/story-writer/weights" \
    --model_type gpt2  \
    --model_name_or_path="/content/drive/My Drive/story-writer/weights" \
    --do_train \
    --train_file="/content/drive/My Drive/story-writer/synopsis_train.txt" \
    --do_eval \
    --validation_file="/content/drive/My Drive/story-writer/synopsis_valid.txt"  \
    --per_device_train_batch_size=32 \
    --per_device_eval_batch_size=32 \
    --overwrite_output_dir
- ### Generation
> !python "/content/drive/My Drive/story-writer/run_generation.py" \
    --model_type gpt2 \
    --model_name_or_path "/content/drive/My Drive/story-writer/weights" \
    --length 100 \
    --prompt "<BOS> The King of Comedy <SEP>" \
    --stop_token "<EOS>" \
    --num_return_sequences 1
## Results
Listing sample outputs for following movie titles 
- ### The King of Comedy
> Set in 1960s Brooklyn, Stoner (Louis Gebhardt), an aging actor named Dave Matthews (Roger Moore), gives a one-man comedy performance. He was cast as a young guy in a portrait of John Cusack but the next scene, shown at a Jewish candlelight vigil, implies that he is leaning toward serious status. After his performance, the audience asks why he is acting, asking why his curtain is drawn but he simply sits and writes on the back.
- ### Armageddon
> Induced by a virus, Humanity has discovered a manner of death called the radiation sickness. K.W. Hughes, a revolutionary scientist with the Natural History Museum (now hosted by MIT), enters the laboratory of a brilliant chemist named Alan Rickman (Eric Dormer), seeking to isolate the virus, using his own body to prepare it for human consumption. Rickman fears for the safety of his alien spacecraft, the Andromeda Interstellar Transport, which Rickman's crew could have used to escape it. With Rickman's help, Rickman encounters an alien virus with a singular genetic code. The alien is able to mutate his body into a human form and devours him. Rickman then becomes the only survivor of Andromeda, while a warning screen has been deployed against all humans as a quarantine zone. A virus does not transmit to humans, so Rickman decides to exterminate the infected, using a machine that has been designed to mutate with such a device.
## Data
GPT2 model is finetune on [MPST dataset](https://arxiv.org/pdf/1802.07858.pdf) which contains synopses of over 14000 movies
## Future Scope
Prompt to also include multiple tags for genre (For eg: Scary Movie, Horror, Comedy)
## Citations
[Huggingface language modelling example](https://github.com/huggingface/transformers/tree/master/examples/language-modeling)
