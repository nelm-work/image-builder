# Image Builder for Cluster API

The Image Builder can be used to build images intended for use with Kubernetes [CAPI](https://cluster-api.sigs.k8s.io/) providers. Each provider has its own format of images that it can work with. For example, AWS instances use AMIs, and vSphere uses OVAs.

For detailed documentation, see https://image-builder.sigs.k8s.io/capi/capi.html.

## 作業ディレクトリに移動

```sh
cd ~/gitops/image-builder/images/capi
```

## 前提条件の依存関係をインストール

```sh
make deps-proxmox
```

**インストール中にエラーが発生した場合は、エラーメッセージに従い必要な依存関係もインストール**

## Proxmoxユーザーにイメージアップロードに必要な権限を付与

Proxmox内で実行

```sh
pveum aclmod / -user capmox@pve -role Administrator
```

## Ubuntu24.04のISOファイルをダウンロードし、Proxmoxにアップロード

```sh
make build-proxmox-ubuntu-2404
```