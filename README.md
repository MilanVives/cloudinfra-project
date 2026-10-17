# Cloud Infrastructure — projectrepository

Dit is jouw persoonlijke projectrepository voor **Cloud Infrastructure** (VIVES, 3CYB).
De volledige opdracht staat op de cursussite: **PE1 — Minikube**.

> ⚠️ Werk in **deze** repository (`VivesMDima/2627-cloudinfra-ti-project-<jouw-username>`), die je via je eigen accept-link kreeg — niet in de template-repository waarop ze gebaseerd is.

## Snel starten

1. Vul `project.yaml` in.
2. Schrijf je Kubernetes manifests in `k8s/` (één map per service).
3. Commit je Secret **niet**: commit enkel `secret.example.yaml` met voorbeeldwaarden.
4. Documenteer in `docs/pe1-minikube.md`, screenshots in `docs/images/`.
5. Dien in: `./scripts/submit.sh` (Windows: in **Git Bash**). Je resultaat verschijnt onder **Releases**.

## Mappen

```
project.yaml           ← jouw gegevens
app/                   ← (optioneel) broncode en Dockerfiles van je applicatie
compose.yaml           ← (optioneel) lokaal testen, niet geëvalueerd
k8s/                   ← PE1: Kubernetes manifests
docs/pe1-minikube.md   ← PE1 documentatie
docs/images/           ← screenshots
scripts/submit.sh      ← indienen
```

## Automatische controles

Elke indiening wordt automatisch gecontroleerd. Op de Releases-pagina zie je per controle PASS/FAIL met uitleg.

### PE1-R0: project.yaml ingevuld

`naam`, `studentennummer` en `github` zijn ingevuld. Vereist voor de andere controles (0 punten).

### PE1-R1: Geldige manifests

Alle YAML in `k8s/` is geldig volgens `kubeconform -strict`, met minstens 3 Deployments/StatefulSets en 3 Services.

### PE1-R2: ConfigMap en Secret correct gebruikt

Minstens één ConfigMap en één Secret, en je workloads gebruiken ze.

### PE1-R3: Geen gevoelige waarden in workloads

Geen wachtwoorden, tokens of keys als letterlijke `value:` in een Deployment of StatefulSet.

### PE1-R4: Deployt in een testcluster

`kubectl apply` van al je manifests in een verse cluster: alle workloads worden Ready.

### PE1-R5: Probes en resources

Elke container heeft een `readinessProbe`, `resources.requests` en `resources.limits`.

### PE1-R6: Documentatie volledig

`docs/pe1-minikube.md` heeft alle verplichte koppen en minstens 3 screenshots die in de repository staan.
