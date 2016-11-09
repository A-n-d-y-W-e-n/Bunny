# Bunny
Some AMQP exercises over Bunny. Please install RabbitMQ and Bunny (Rubygem) first.


## Installing RabbitMQ on Homebrew

A brew for the RabbitMQ server is available from Homebrew.

> Note: You may not be able to install the RabbitMQ brew from inside a firewall.
Install the Server

Before installing make sure you have the latest brews:


    brew update

Then, install RabbitMQ server with:


    brew install rabbitmq

## Run RabbitMQ Server

The RabbitMQ server scripts are installed into `/usr/local/sbin` . This is not automatically added to your path, so you may wish to add `PATH=$PATH:/usr/local/sbin` to your `.bash_profile` or `.profile` . The server can then be started with rabbitmq-server.

All scripts run under your own user account. Sudo is not required.


> You should be able to run `/usr/local/sbin/rabbitmq-server` or add it to your path to run it anywhere.
> Your command failed because, by default, `.` is not on your `$PATH`. You went to the right directory (`/usr/local/sbin`) and wanted to run the `rabbitmq-server` that existed and had exec permissions, but by typing `rabbitmq-server` as a command Unix only searches for that command on your `$PATH` directories - which didn't include `/usr/local/sbin`.
> What you wanted to do can be achieved by typing `./rabbitmq-server` - say, execute the `rabbitmq-server` program that is in the current directory. That's analogous to running `/usr/local/sbin/rabbitmq-server` from everywhere - `.` represents your current directory, so it's the same as `/usr/local/sbin` in that context.

As rabbitmq-server resides in `/usr/local/sbin`, running this command will enable starting server from anywhere:


    export PATH=/usr/local/sbin:$PATH

修改`$PATH` 參數方法：


    touch ~/.bash_profile; open ~/.bash_profile

加入以下指令並儲存：


    export PATH="/usr/local/sbin:$PATH"

強迫執行 `.bash_profile` ：


    source ~/.bash_profile

此時可輸數以下數據確認已加入路徑參數：


    echo $PATH

接著就可以在任何路徑下執行 RabbitMQ 了！

----------

執行：


    rabbitmq-server

停止：


    rabbitctl-stop


## To install Bunny with RubyGems

    gem install bunny
