aleo smart contract

pre code aleo
------------------------------------------------------------------
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

source $HOME/.cargo/env

rustup install stable

rustup update stable

rustup default stable

git clone https://github.com/AleoHQ/leo
cd leo

apt install clang gcc libssl-dev pkg-config

cargo install --path .

git clone https://github.com/AleoHQ/snarkOS.git --depth 1
cd snarkOS

./build_ubuntu.sh

cargo install --path .

sms for fauset
------------------------------------------------------------------

@AleoFaucet send 10 credits to aleo1y9s2yr50paljp0rd8wtqzy6ue9cshyyukwfslx2vhpj588vnguzqnndumr

chrome
https://chrome.google.com/webstore/detail/json-beautifier-editor/lpopeocbeepakdnipejhlpcmifheolpl
------------------------------------------------------------------

cd $HOME

mkdir demo_deploy_Leo_app && cd demo_deploy_Leo_app

WALLETADDRESS="aleo1a7uu7d4aat8vk3prckkeam89r98cw6k28pflnsyhy8z0ft2w45zqwqzgn2"

APPNAME=askhariin_"${WALLETADDRESS:4:6}"

leo new "${APPNAME}"

PATHTOAPP=$(realpath -q $APPNAME)

cd $PATHTOAPP && cd ..

PRIVATEKEY="APrivateKey1zkpCnsVgjh754U5G7DQdF4xarkA329MB4xGFZkuk6YQ3MV4"

RECORD=""

snarkos developer deploy "${APPNAME}.aleo" --private-key "${PRIVATEKEY}" --query "https://vm.aleo.org/api" --path "./${APPNAME}/build/" --broadcast "https://vm.aleo.org/api/testnet3/transaction/broadcast" --fee 600000 --record "${RECORD}"

# askhar
