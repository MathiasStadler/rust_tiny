# project path
<!-- keep the format -->
>[!NOTE]
>Approvement of [![alt text][1]](https://github.com/MathiasStadler/try_out_egui_plot/blob/master/project_path.md?plain=1)
<!-- keep the format -->
>[!NOTE]
>Use codium of debian
><!-- To comply with the format -->
>```bash <!-- markdownlint-disable-line code-block-style -->
>codium --user-data-dir /home/trapapa/codium_one/ --extensions-dir /home/trapapa/codium_one/extensions_one --log debug --profile my_one
>```
>
<!-- kep the format -->
TODO: complete extension
>[!NOTE]
>Use follow extensions
>-list-extensions List the installed extensions
><!-- To comply with the format -->
>```bash <!-- markdownlint-disable-line code-block-style -->
>codium -list-extensions # List the installed extensions
>
>```
>
<!-- keep the format -->
## Create for your own project a new project folder in the console(terminal, bash shell)
<!-- keep the format -->
- e.g. in your own home folder, and open it as a new project inside your program used - in my case for MS VSCode / MS VSCodium
- change in your own project folder
<!-- To comply with the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
# cd <own project folder>
pwd
project_name="new_project"
echo ${project_name} 
# cd && mkdir <project_name> folder> && cd $_
# command 'cd' change to home folder from logged in user
# command 'mkdir' create the DIRECTORY(ies), if they do not already exist
# command `cd` <folder>`change to the folder
# command '$_' last argument of last command
mkdir ${project_name} && cd $_
```
<!-- keep the format -->
## Create a new rust based project inside the previously generated folder and update the rust binary's system wide to the last stable version
<!-- -->
```bash <!-- markdownlint-disable-line code-block-style -->
touch README.md \
&& ln -s README.md README \
&& cargo init "." \
&& cargo add rustfmt \
&& rustup component add rustfmt \
&& mkdir examples \
&& cp src/main.rs examples/example.rs \
&& sed -i -e 's/world/example/g' examples/example.rs \
&& rustup show \
&& rustup check \
&& rustup toolchain uninstall stable \
&& rustup toolchain install stable \
&& rustup update  --force \
&& rustup show \
&& mkdir tests \
&& rustup override set stable \
&& rustup show |sed -n '/active toolchain/,/^$/p'
```
<!-- keep the format -->
<!-- keep the format -->
## Show which toolchain is active
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustup show
# or better
rustup show |sed -n '/active toolchain/,/^$/p'
```
<!-- keep the format -->
## Set/switch  rust toolchain - switch stable to nightly and back
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustup override set nightly
#or
rustup override set stable
```
<!-- keep the format -->
## Show rustc version verbose
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustc --version --verbose
```
<!-- keep the format -->
>[!NOTE]
> Make sure the stable toolchain is activated
<!-- keep the format -->
>[!TIP] Markdownlint - Rules inside files can be enabled, disabled
> <!-- markdownlint-disable-next-line --> [![alt text][1]](https://github.com/DavidAnson/markdownlint)
<!-- keep the format -->
## Clean the project - remove every things inside the target folder
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo clean
```
<!-- keep the format -->
## Build the project - debug
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo build
```
<!-- keep the format -->
## Run the project - debug
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
>cargo run
 Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.05s
     Running `target/debug/rust_tiny`
Hello, world! - rust-tiny
# or direct path
./target/debug/rust_tiny
# size of binary
> du -sh ./target/debug/rust_tiny
 3.7M    ./target/debug/rust_tiny
```
<!-- keep the format -->
## Build the project - release
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo build --release
```
<!-- keep the format -->
## Run the project - release
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
>cargo run --release
    Finished `release` profile [optimized] target(s) in 0.06s
     Running `target/release/rust_tiny`
Hello, world! - rust-tiny
# or direct path change to project_folder
./target/release/rust_tiny
# size of binary
> du -sh ./target/release/rust_tiny
 432K    ./target/release/rust_tiny
```
<!-- keep the format -->
>[!NOTE]
> 89% smaller file size
<!-- keep the format -->
## Add inside Cargo.toml strip = true option
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
[profile.release]
strip = true 
```
<!-- keep the format -->
## Build the project - release - [profile.release] strip = true
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo build --release
```
<!-- keep the format -->
## Run the project - release- [profile.release] strip = true  
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
>cargo run --release
    Finished `release` profile [optimized] target(s) in 0.06s
     Running `target/release/rust_tiny`
Hello, world! - rust-tiny
# or direct path change to project_folder
./target/release/rust_tiny
# size of binary
> du -sh ./target/release/rust_tiny
 360K    ./target/release/rust_tiny
```
<!-- keep the format -->
>[!NOTE]
> 17% smaller execute file size

##
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo build
```
<!-- keep the format -->
## Run the project
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo run
# naive path of execute
# <project_folder>/target/debug/try-out-eframe-real-time-plotting
# cd <project_folder>
target/debug/try-out-eframe-real-time-plotting
```
<!-- keep the format -->
## File size of executable
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
ls -lah target/debug/try-out-eframe-real-time-plotting
```
<!-- keep the format -->
## Build the project - release
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo build --release
```
<!-- keep the format -->
## Run the project - release
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo run - release
# or direct path
target/release/try-out-eframe-real-time-plotting
```
<!-- keep the format -->
## File size of executable -release
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
ls -lah target/release/try-out-eframe-real-time-plotting
```
<!-- keep the format -->
>[!NOTE]
>File size differences between the executable debug and release version 10/1
> debug -  3825448 kb
> release - 442176 kb
<!-- keep the format -->
<!-- keep the format -->
<!-- make folder and download the link sign vai curl -->
<!-- mkdir -p img && curl --create-dirs --output-dir img -O  "https://raw.githubusercontent.com/MathiasStadler/link_symbol_svg/refs/heads/main/link_symbol.svg"-->
<!-- Link sign - Don't Found a better way :-( - You know a better method? - send me a email -->
[1]: ./img/link_symbol.svg
<!-- keep the format -->