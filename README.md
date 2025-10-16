Absolutely! Here’s a **short, clear step-by-step guide** to access your OKE cluster:

---

# **Access OKE Cluster — Step by Step**

### **1️⃣ Install OCI CLI (if not already)**

```bash
bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
oci -v  # verify installation
```

---

### **2️⃣ Create kubeconfig for your OKE cluster**

```bash
mkdir -p $HOME/.kube

oci ce cluster create-kubeconfig \
  --cluster-id ocid1.cluster.oc1.iad..............IDDD,,,,,,,,,,, \
  --file $HOME/.kube/config \
  --region us-ashburn-1 \
  --token-version 2.0.0 \
  --kube-endpoint PUBLIC_ENDPOINT
```

---

### **3️⃣ Set KUBECONFIG environment variable**

```bash
export KUBECONFIG=$HOME/.kube/config
```

---

### **4️⃣ Verify connection**

```bash
kubectl config get-contexts
kubectl config current-context
kubectl get nodes
```

✅ You should see your OKE worker nodes with `STATUS=Ready`.

---

### **5️⃣ Switch between clusters (optional)**

* Switch to OKE:

```bash
kubectl config use-context context-cvmvvzfghva
```

* Switch to Minikube:

```bash
kubectl config use-context minikube
```

---

### **6️⃣ Optional — check cluster info**

```bash
kubectl cluster-info
```

Shows API endpoint and core services running.

---

This is all you need to **access and manage your OKE cluster**.

---

If you want, I can also make a **super short 1-page “cheat sheet” with commands only** that you can keep in front of you while working with OKE. It will be super handy.

Do you want me to make that?
