FROM tensorflow/tensorflow:1.5.0-gpu

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git 
RUN git clone https://github.com/tensorflow/nmt
WORKDIR "nmt"
RUN mkdir data
COPY data data
RUN touch abc.txt
RUN git checkout tf-1.4 &&  python -m nmt.nmt --src=code --tgt=comment --vocab_prefix=data/vocab --train_prefix=data/train --dev_prefix=data/valid --test_prefix=data/test --out_dir=output --num_train_steps=5000 --steps_per_stats=2000 --num_layers=2 --num_units=512 --dropout=0.5 --metrics=bleu --learning_rate=0.5 --decay_factor=0.99 --max_gradient_norm=5.0
