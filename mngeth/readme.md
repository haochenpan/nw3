## Geth + Mininet Project

### Steps to Install & Use
 
- populate a VM instance with Ubuntu 18.04 LTS, ***# of cpus >= # of Mininet hosts to be used + 1*** (the extra core is for the Mininet's main process)

- execute the following
    ```shell script
    sudo su # mininet requires the root priviledge
    cd
    git clone https://github.com/haochenpan/nw3.git
    cd nw3/mngeth
    . setup.sh # to install Go environment, Geth, and Mininet
    . run.sh 5 # to start evaluation with 5 miners, replace 5 with any other natural number
    ```
 
 
### Project Structure
- data/: store all log files for the analysis program to calculate throughputs and latencies
- hosts/: store all geth miner runtime data
- keys/: store all pre generated keys (may deprecate in the future)
- v2/
    - v2_config.yaml: Config Mininet topology and link parameters. 
    Explanation see [here](https://github.com/haochenpan/nw3/blob/57bd04294abaf5c9af5eedddc1ac7616f132ff3b/mngeth/config.yaml).
    ***Let # of Mininet hosts >= # of miners, i.e. the paramter after `. run.sh`***
- analysis.sh: the analysis program that calculates throughputs and latencies, called by run.sh
- genesis.json: Etherum Genesis Block's definition
- prerun2.sh: prepare Geth miners' folders, environment variables, called by run.sh
- run.sh: the entry point of an evaluation
- setup.sh: install this project

