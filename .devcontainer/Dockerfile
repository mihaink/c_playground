# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.192.0/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version: bullseye, buster, stretch
ARG VARIANT="buster"
ARG LLVM="13"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# ** [Optional] Uncomment this section to install additional packages. **
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends software-properties-common


# Add the repository key
RUN wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add -

# Add the LLVM repository; the -s flag also adds the source repository to the /etc/apt/sources file.
RUN apt-add-repository -s "deb http://apt.llvm.org/bullseye/ llvm-toolchain-bullseye-13 main"

# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends clang-13 lldb-13 lld-13

# LLVM
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libllvm-13-ocaml-dev libllvm13 llvm-13 llvm-13-dev llvm-13-doc llvm-13-runtime

# Clang and co
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends clang-13 clang-tools-13 clang-13-doc libclang-common-13-dev libclang-13-dev libclang1-13 clang-format-13 clangd-13

# libfuzzer
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libfuzzer-13-dev

# lldb
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends lldb-13

# lld (linker)
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends lld-13

# libc++
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libc++-13-dev libc++abi-13-dev

# OpenMP
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libomp-13-dev

# libclc
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libclc-13-dev

# libunwind
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libunwind-13-dev

RUN ln -s /usr/bin/clang-13 /usr/bin/clang