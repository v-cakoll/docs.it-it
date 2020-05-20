---
title: Sicurezza di Azure per app native del cloud
description: Architettura di app .NET cloud native per Azure | Sicurezza di Azure per le app cloud native
ms.date: 05/13/2020
ms.openlocfilehash: a39b64477eb9e896c6603e5609ede653bfee1e07
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614253"
---
# <a name="azure-security-for-cloud-native-apps"></a>Sicurezza di Azure per app native del cloud

Le applicazioni native del cloud possono essere più semplici e più difficili da proteggere rispetto alle applicazioni tradizionali. Sul lato negativo, è necessario proteggere applicazioni più piccole e dedicare maggiore energia per creare l'infrastruttura di sicurezza. La natura eterogenea dei linguaggi di programmazione e degli stili nella maggior parte delle distribuzioni di servizi comporta inoltre la necessità di prestare maggiore attenzione ai bollettini sulla sicurezza di diversi provider.

Sul lato flip, i servizi più piccoli, ognuno con il proprio archivio dati, limitano l'ambito di un attacco. Se un utente malintenzionato compromette un sistema, è probabilmente più difficile per l'autore dell'attacco passare a un altro sistema rispetto a un'applicazione monolitica. I limiti del processo sono limiti forti. Inoltre, in caso di perdita di un backup del database, il danno è più limitato perché il database contiene solo un subset di dati e non può contenere dati personali.

## <a name="threat-modeling"></a>Modellazione delle minacce

Indipendentemente dal fatto che i vantaggi superino gli svantaggi delle applicazioni native del cloud, è necessario seguire la stessa mentalità olistica per la sicurezza. La sicurezza e il pensiero sicuro devono far parte di ogni fase della storia di sviluppo e operatività. Quando si pianifica un'applicazione, porre domande come:

- Qual è l'effetto della perdita dei dati?
- In che modo è possibile limitare i danni causati da dati danneggiati da inserire in questo servizio?
- Utenti autorizzati ad accedere a questi dati
- Sono disponibili criteri di controllo per il processo di sviluppo e rilascio?

Tutte queste domande fanno parte di un processo denominato [modellazione dei rischi](https://docs.microsoft.com/azure/security/azure-security-threat-modeling-tool). Questo processo prova a rispondere alla domanda di quali sono le minacce al sistema, alla probabilità che si verifichino le minacce e ai potenziali danni.

Una volta stabilito l'elenco delle minacce, è necessario decidere se è opportuno attenuarle. A volte una minaccia è così improbabile e costosa da pianificare perché non vale la pena spendere energia. Ad esempio, un attore del livello di stato potrebbe inserire le modifiche nella progettazione di un processo usato da milioni di dispositivi. A questo punto, invece di eseguire una determinata parte di codice nell' [anello 3](https://en.wikipedia.org/wiki/Protection_ring), il codice viene eseguito nell'anello 0. Questo consente un exploit che può ignorare l'hypervisor ed eseguire il codice di attacco sui computer bare metal, consentendo attacchi su tutte le macchine virtuali in esecuzione su tale hardware.

I processori modificati sono difficili da rilevare senza un microscopio e una conoscenza avanzata della progettazione del processore in silicone. Questo scenario è improbabile e costoso da mitigare, quindi probabilmente nessun modello di minaccia suggerisce la creazione della protezione dagli exploit.

Minacce più probabili, ad esempio i controlli di accesso interrotti che consentono `Id` di incrementare gli attacchi (sostituendo `Id=2` con `Id=3` nell'URL) o SQL injection, sono più interessanti per la creazione di protezioni da. Le mitigazioni per queste minacce sono piuttosto ragionevoli per la creazione e la prevenzione di problemi di sicurezza imbarazzanti che informano la reputazione dell'azienda.

## <a name="principle-of-least-privilege"></a>Principio dei privilegi minimi

Una delle idee più rilevate nella sicurezza dei computer è il principio del privilegio minimo (POLP). Si tratta in realtà di un'idea fondamentale nella maggior parte dei casi di sicurezza, sia digitale che fisica. In breve, il principio è che qualsiasi utente o processo deve avere il minor numero di diritti possibile per eseguire la relativa attività.

Si pensi ad esempio ai cassieri di una banca: l'accesso al Safe è un'attività non comune. Quindi, la cassiera media non può aprire la cassaforte. Per ottenere l'accesso, è necessario inoltrare la richiesta tramite un responsabile della banca che esegue controlli di sicurezza aggiuntivi.

In un sistema informatico, un esempio fantastico è costituito dai diritti di un utente che si connette a un database. In molti casi, è disponibile un singolo account utente che consente di compilare la struttura del database ed eseguire l'applicazione. Ad eccezione dei casi estremi, l'account che esegue l'applicazione non necessita della possibilità di aggiornare le informazioni sullo schema. Dovrebbero essere presenti diversi account che forniscono diversi livelli di privilegio. L'applicazione deve utilizzare solo il livello di autorizzazione che concede l'accesso in lettura e scrittura ai dati nelle tabelle. Questo tipo di protezione eliminerà gli attacchi che miravano a eliminare le tabelle di database o a introdurre trigger dannosi.

Quasi tutte le parti della creazione di un'applicazione nativa del cloud possono trarre vantaggio dalla memorizzazione del principio dei privilegi minimi. È possibile trovarlo quando si configurano i firewall, i gruppi di sicurezza di rete, i ruoli e gli ambiti nel controllo degli accessi in base al ruolo (RBAC).

## <a name="penetration-testing"></a>Test di penetrazione

Man mano che le applicazioni diventano più complesse, il numero di vettori di attacco aumenta a una velocità allarmante. La modellazione delle minacce è difettosa in quanto tende a essere eseguita dalle stesse persone che compilano il sistema. Nello stesso modo in cui molti sviluppatori riscontrano problemi durante la progettazione delle interazioni utente e quindi compilano interfacce utente inutilizzabili, la maggior parte degli sviluppatori ha difficoltà a osservare ogni vettore di attacco. È anche possibile che gli sviluppatori che compilano il sistema non siano in grado di affrontare le metodologie di attacco e perdano qualcosa di fondamentale.

Il test di penetrazione o il "test di penna" comporta l'inserimento di attori esterni per tentare di attaccare il sistema. Questi utenti malintenzionati possono essere una società di consulenza esterna o altri sviluppatori con una conoscenza di sicurezza di un'altra parte dell'azienda. A loro viene assegnata una carta bianca per tentare di sovvertire il sistema. Spesso, troveranno buchi di sicurezza completi che devono essere corretti. Talvolta il vettore di attacco è qualcosa di imprevisto, ad esempio sfruttando un attacco di phishing contro il CEO.

Azure è costantemente in corso di attacchi da parte [di un team di hacker di Microsoft](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/). Nel corso degli anni sono stati i primi a trovare dozzine di vettori di attacco potenzialmente catastrofici, chiuderli prima che possano essere sfruttati esternamente. Maggiore è la tentazione di una destinazione, maggiore è la probabilità che gli attori eterni tentino di sfruttarla e che ci siano alcuni obiettivi più accattivanti rispetto ad Azure.

## <a name="monitoring"></a>Monitoraggio

Se un utente malintenzionato tenta di penetrare in un'applicazione, dovrebbe essere presente un messaggio di avviso. Spesso è possibile individuare gli attacchi esaminando i log dei servizi. Gli attacchi lasciano segni di rivelamento che possono essere individuati prima che abbiano esito positivo. Ad esempio, un utente malintenzionato che tenta di indovinare una password effettuerà molte richieste a un sistema di accesso. Il monitoraggio del sistema di accesso è in grado di rilevare modelli bizzarri che non rientrano nel modello di accesso tipico. Questo monitoraggio può essere trasformato in un avviso che può, a sua volta, avvisare un operatore operativo per attivare una sorta di contromisura. Un sistema di monitoraggio estremamente maturo potrebbe anche intervenire in base a queste deviazioni in modo proattivo aggiungendo regole per bloccare le richieste o limitare le risposte.

## <a name="securing-the-build"></a>Sicurezza della compilazione

Una delle posizioni in cui la sicurezza è spesso trascurata è il processo di compilazione. Non solo i controlli di sicurezza dell'esecuzione della compilazione, ad esempio l'analisi di codice non sicuro o credenziali archiviate, ma la compilazione stessa dovrebbe essere sicura. Se il server di compilazione è compromesso, fornisce un vettore fantastico per l'introduzione di codice arbitrario nel prodotto.

Si supponga che un utente malintenzionato stia cercando di rubare le password degli utenti che accedono a un'applicazione Web. Potrebbero introdurre un'istruzione di compilazione che modifichi il codice estratto per eseguire il mirroring di qualsiasi richiesta di accesso a un altro server. La volta successiva che il codice passa attraverso la compilazione, viene aggiornato in modo invisibile all'utente. L'analisi delle vulnerabilità del codice sorgente non rileva questa condizione mentre viene eseguita prima della compilazione. Allo stesso modo, nessuno lo rileverà in una revisione del codice perché le fasi di compilazione si trovano nel server di compilazione. Il codice sfruttato passerà all'ambiente di produzione in cui è possibile raccogliere le password. Probabilmente non è presente alcun log di controllo delle modifiche del processo di compilazione o almeno nessuno monitora il controllo.

Si tratta di un esempio perfetto di una destinazione di valore apparentemente bassa che può essere usata per suddividere nel sistema. Una volta che un utente malintenzionato ha violato il perimetro del sistema, può iniziare a lavorare per trovare modi per elevare le loro autorizzazioni al punto in cui possono causare danni reali ovunque si trovino.

## <a name="building-secure-code"></a>Creazione di codice sicuro

.NET Framework è già un Framework abbastanza sicuro. Evita alcuni problemi del codice non gestito, ad esempio l'analisi delle estremità delle matrici. Il lavoro viene svolto attivamente per correggere i problemi di sicurezza non appena vengono individuati. Esiste anche un [programma di Bounty dei bug](https://www.microsoft.com/msrc/bounty) che consente ai ricercatori di individuare i problemi del Framework e di segnalarli anziché sfruttarli.

Esistono diversi modi per rendere più sicuro il codice .NET. Le linee guida seguenti, ad esempio le [linee guida per la codifica sicura per .NET](https://docs.microsoft.com/dotnet/standard/security/secure-coding-guidelines) , sono un'operazione ragionevole da eseguire per garantire che il codice sia protetto da zero. [OWASP Top 10](https://owasp.org/www-project-top-ten/) è un'altra guida preziosa per la creazione di codice sicuro.

Il processo di compilazione è una posizione ideale per inserire gli strumenti di analisi per rilevare i problemi nel codice sorgente prima di crearli nell'ambiente di produzione. La maggior parte di ogni progetto ha dipendenze da altri pacchetti. Uno strumento che consente di analizzare i pacchetti obsoleti rileverà i problemi in una compilazione notturna. Anche quando si compilano immagini Docker, è utile controllare e verificare che l'immagine di base non abbia vulnerabilità note. Un altro aspetto da controllare è che nessuno ha accidentalmente archiviato le credenziali.

## <a name="built-in-security"></a>Sicurezza integrata

Azure è progettato per bilanciare l'usabilità e la sicurezza per la maggior parte degli utenti. Utenti diversi avranno requisiti di sicurezza diversi, quindi dovranno ottimizzare il proprio approccio alla sicurezza del cloud. Microsoft pubblica una grande quantità di informazioni di sicurezza nel [centro](https://azure.microsoft.com/support/trust-center/)protezione. Questa risorsa dovrebbe essere la prima tappa per i professionisti interessati a comprendere il funzionamento delle tecnologie di mitigazione degli attacchi incorporate.

All'interno del portale di Azure, il [Azure Advisor](https://azure.microsoft.com/services/advisor/) è un sistema che esegue costantemente la scansione di un ambiente e le raccomandazioni. Alcuni di questi consigli sono progettati per risparmiare denaro agli utenti, mentre altri sono progettati per identificare configurazioni potenzialmente non sicure, ad esempio un contenitore di archiviazione aperto al mondo e non protetto da una rete virtuale.

## <a name="azure-network-infrastructure"></a>Infrastruttura di rete di Azure

In un ambiente di distribuzione locale, una grande quantità di energia è dedicata alla configurazione della rete. La configurazione di router, commutatori e di questo tipo è un lavoro complesso. Le reti consentono a determinate risorse di comunicare con altre risorse e di impedire l'accesso in alcuni casi. Una regola di rete frequente consiste nel limitare l'accesso all'ambiente di produzione dall'ambiente di sviluppo, in caso di mancata esecuzione di un frammento di codice parzialmente sviluppato che elimina una fascia di dati.

Per impostazione predefinita, la maggior parte delle risorse di Azure PaaS ha solo la configurazione di rete più semplice e permissiva. Ad esempio, chiunque su Internet può accedere a un servizio app. Le nuove istanze di SQL Server vengono in genere limitate, in modo che le parti esterne non possano accedervi, ma gli intervalli di indirizzi IP usati da Azure sono consentiti tramite. Quindi, sebbene SQL Server sia protetto da minacce esterne, un utente malintenzionato deve solo configurare una testa di ponte di Azure da cui possano avviare attacchi contro tutte le istanze di SQL in Azure.

Fortunatamente, la maggior parte delle risorse di Azure può essere posizionata in una rete virtuale di Azure che consente il controllo degli accessi con granularità fine. Analogamente al modo in cui le reti locali stabiliscono reti private protette dal mondo più ampio, le reti virtuali sono isole di indirizzi IP privati che si trovano all'interno della rete di Azure.

![Figura 9-1 una rete virtuale in Azure](./media/virtual-network.png)

**Figura 9-1**. Una rete virtuale in Azure.

Nello stesso modo in cui le reti locali hanno un firewall che controlla l'accesso alla rete, è possibile stabilire un firewall simile al limite della rete virtuale. Per impostazione predefinita, tutte le risorse in una rete virtuale possono comunque comunicare con Internet. Sono solo le connessioni in ingresso che richiedono una qualche forma di eccezione esplicita del firewall.

Con la rete stabilita, è possibile configurare risorse interne come gli account di archiviazione in modo da consentire l'accesso solo a risorse che si trovano anche nella rete virtuale. Questo firewall fornisce un livello aggiuntivo di sicurezza, in caso di perdita delle chiavi per l'account di archiviazione, gli utenti malintenzionati non sarebbero in grado di connettersi a tale account per sfruttare le chiavi perse. Si tratta di un altro esempio del principio del privilegio minimo.

I nodi in un cluster Azure Kubernetes possono partecipare a una rete virtuale come ad altre risorse più native di Azure. Questa funzionalità è denominata [interfaccia di rete del contenitore di Azure](https://github.com/Azure/azure-container-networking/blob/master/docs/cni.md). In effetti, alloca una subnet all'interno della rete virtuale in cui sono allocate le macchine virtuali e le immagini del contenitore.

Continuando il percorso di illustrare il principio dei privilegi minimi, non tutte le risorse all'interno di una rete virtuale devono comunicare con tutte le altre risorse. Ad esempio, in un'applicazione che fornisce un'API Web su un account di archiviazione e un database SQL, è improbabile che il database e l'account di archiviazione debbano comunicare tra loro. La condivisione dei dati tra di essi passa attraverso l'applicazione Web. Quindi, è possibile usare un [gruppo di sicurezza di rete (NSG)](https://docs.microsoft.com/azure/virtual-network/security-overview) per negare il traffico tra i due servizi.

Un criterio per negare la comunicazione tra le risorse può essere fastidioso da implementare, soprattutto in base all'uso di Azure senza restrizioni di traffico. In alcuni altri cloud il concetto di gruppi di sicurezza di rete è molto più prevalente. Ad esempio, il criterio predefinito in AWS è che le risorse non possono comunicare tra loro fino a quando non sono abilitate da regole in un NSG. Sebbene sia più lento sviluppare questo, un ambiente più restrittivo fornisce un valore predefinito più sicuro. L'uso di procedure DevOps appropriate, in particolare l'uso di [Azure Resource Manager o di bonifica](infrastructure-as-code.md) per gestire le autorizzazioni può rendere più semplice il controllo delle regole.

Le reti virtuali possono essere utili anche quando si configura la comunicazione tra le risorse locali e quelle cloud. Una rete privata virtuale può essere usata per connettere facilmente le due reti. In questo modo è possibile eseguire una rete virtuale senza gateway per gli scenari in cui tutti gli utenti sono in sede. Per stabilire questa rete è possibile utilizzare diverse tecnologie. Il più semplice consiste nell'usare una [VPN da sito a sito](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#s2smulti) che può essere stabilita tra molti router e Azure. Il traffico viene crittografato ed effettuato tramite tunneling su Internet con lo stesso costo per byte di qualsiasi altro traffico. Per gli scenari in cui è auspicabile una maggiore larghezza di banda o maggiore sicurezza, Azure offre un servizio denominato [Express Route](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#ExpressRoute) che usa un circuito privato tra una rete locale e Azure. È più costoso e difficile da stabilire ma anche più sicuro.

## <a name="role-based-access-control-for-restricting-access-to-azure-resources"></a>Controllo degli accessi in base al ruolo per limitare l'accesso alle risorse di Azure

RBAC è un sistema che fornisce un'identità alle applicazioni in esecuzione in Azure. Le applicazioni possono accedere alle risorse utilizzando questa identità anziché o in aggiunta all'utilizzo di chiavi o password.

## <a name="security-principals"></a>Entità di sicurezza

Il primo componente di RBAC è un'entità di sicurezza. Un'entità di sicurezza può essere un utente, un gruppo, un'entità servizio o un'identità gestita.

![Figura 9-2 tipi diversi di entità di sicurezza](./media/rbac-security-principal.png)

**Figura 9-2**. Tipi diversi di entità di sicurezza.

- Utente: qualsiasi utente che dispone di un account in Azure Active Directory è un utente.
- Group: raccolta di utenti da Azure Active Directory. Come membro di un gruppo, un utente assume i ruoli del gruppo in aggiunta ai rispettivi.
- Entità servizio: identità di sicurezza in cui vengono eseguiti i servizi o le applicazioni.
- Identità gestita: identità Azure Active Directory gestita da Azure. Le identità gestite vengono in genere usate quando si sviluppano applicazioni cloud che gestiscono le credenziali per l'autenticazione ai servizi di Azure.

L'entità di sicurezza può essere applicata alla maggior parte delle risorse. Ciò significa che è possibile assegnare un'entità di sicurezza a un contenitore in esecuzione in Azure Kubernetes, consentendo l'accesso ai segreti archiviati in Key Vault. Una funzione di Azure può assumere un'autorizzazione che consente di comunicare con un'istanza di Active Directory per convalidare un JWT per un utente chiamante. Una volta abilitati i servizi con un'entità servizio, le autorizzazioni possono essere gestite in modo granulare tramite ruoli e ambiti.

## <a name="roles"></a>Ruoli

Un'entità di sicurezza può assumere molti ruoli o, usando un'analogia sartoriale, ha molti cappelli. Ogni ruolo definisce una serie di autorizzazioni, ad esempio "leggere i messaggi dall'endpoint del bus di servizio di Azure". Il set di autorizzazioni valide di un'entità di sicurezza è la combinazione di tutte le autorizzazioni assegnate a tutti i ruoli dell'entità di sicurezza. Azure dispone di un numero elevato di ruoli predefiniti e gli utenti possono definire i propri ruoli.

![Figura 9-3 definizioni di ruolo RBAC](./media/rbac-role-definition.png)

**Figura 9-3**. Definizioni di ruolo RBAC.

Incorporati in Azure sono anche un numero di ruoli di alto livello, ad esempio proprietario, collaboratore, lettore e amministratore account utente. Con il ruolo proprietario, un'entità di sicurezza può accedere a tutte le risorse e assegnare le autorizzazioni ad altri utenti. Un collaboratore ha lo stesso livello di accesso a tutte le risorse, ma non può assegnare autorizzazioni. Un lettore può solo visualizzare le risorse di Azure esistenti e un amministratore dell'account utente può gestire l'accesso alle risorse di Azure.

I ruoli predefiniti più granulari, come il [collaboratore zona DNS](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles#dns-zone-contributor) , hanno diritti limitati a un singolo servizio. Le entità di sicurezza possono assumere un numero qualsiasi di ruoli.

## <a name="scopes"></a>Ambiti

I ruoli possono essere applicati a un set limitato di risorse in Azure. Ad esempio, applicando l'ambito all'esempio precedente di lettura da una coda del bus di servizio, è possibile limitare l'autorizzazione a una singola coda: "leggere i messaggi dall'endpoint del bus di servizio di Azure `blah.servicebus.windows.net/queue1` "

L'ambito può essere limitato come una singola risorsa oppure può essere applicato a un intero gruppo di risorse, una sottoscrizione o un gruppo di gestione.

Quando si esegue il test se un'entità di sicurezza dispone di un'autorizzazione specifica, viene presa in considerazione la combinazione di ruolo e ambito. Questa combinazione fornisce un potente meccanismo di autorizzazione.

## <a name="deny"></a>Nega

In precedenza erano consentite solo le regole "Allow" per RBAC. Questo comportamento rendeva complicate le compilazioni degli ambiti. Ad esempio, per consentire a un'entità di sicurezza di accedere a tutti gli account di archiviazione, ad eccezione di uno, è necessario concedere l'autorizzazione esplicita a un elenco potenzialmente infinito di account di archiviazione Ogni volta che viene creato un nuovo account di archiviazione, è necessario aggiungerlo a questo elenco di account. Questo ulteriore sovraccarico di gestione che certamente non era auspicabile.

Le regole Deny hanno la precedenza sulle regole Allow. Ora rappresenta lo stesso ambito "Consenti tutto tranne uno" può essere rappresentato come due regole "Consenti tutto" e "nega questo uno specifico". Negare le regole non solo semplifica la gestione, ma consente le risorse più sicure negando l'accesso a tutti gli utenti.

## <a name="checking-access"></a>Verifica dell'accesso

Come si può immaginare, avere un numero elevato di ruoli e ambiti può rendere piuttosto difficile l'autorizzazione efficace di un'entità servizio. L'accumulo di regole di negazione, serve solo per aumentare la complessità. Fortunatamente, è disponibile un calcolatore delle autorizzazioni che consente di visualizzare le autorizzazioni valide per qualsiasi entità servizio. Si trova in genere nella scheda IAM del portale, come illustrato nella figura 10-3.

![Figura 9-4 calcolatore delle autorizzazioni per un servizio app](./media/check-rbac.png)

**Figura 9-4**. Calcolatore delle autorizzazioni per un servizio app.

## <a name="securing-secrets"></a>Protezione dei segreti

Le password e i certificati rappresentano un vettore di attacco comune per gli utenti malintenzionati. L'hardware con cracking delle password può eseguire un attacco di forza bruta e provare a indovinare miliardi di password al secondo. È quindi importante che le password usate per accedere alle risorse siano complesse, con una grande varietà di caratteri. Queste password sono esattamente il tipo di password quasi impossibile da ricordare. Fortunatamente, le password in Azure non devono essere effettivamente note a tutti gli utenti.

Molti esperti di sicurezza [suggeriscono](https://www.troyhunt.com/password-managers-dont-have-to-be-perfect-they-just-have-to-be-better-than-not-having-one/) che l'uso di un gestore di password per tenere le proprie password è l'approccio migliore. Mentre centralizza le password in un'unica posizione, consente anche l'uso di password estremamente complesse e garantisce che siano univoche per ogni account. Lo stesso sistema esiste in Azure: un archivio centrale per i segreti.

## <a name="azure-key-vault"></a>Insieme di credenziali chiave di Azure

Azure Key Vault fornisce una posizione centralizzata per archiviare le password per elementi quali database, chiavi API e certificati. Una volta immesso un segreto nell'insieme di credenziali, non viene mai visualizzato di nuovo e i comandi da estrarre e visualizzare sono volutamente complicati. Le informazioni in Safe sono protette tramite la crittografia software o i moduli di protezione hardware convalidati FIPS 140-2 Level 2.

L'accesso all'insieme di credenziali delle chiavi viene fornito tramite RBAC, vale a dire che non solo tutti gli utenti possono accedere alle informazioni nell'insieme di credenziali. Si consideri un'applicazione Web che desidera accedere alla stringa di connessione del database archiviata in Azure Key Vault. Per ottenere l'accesso, le applicazioni devono essere eseguite usando un'entità servizio. Con questo ruolo assunto possono leggere i segreti dalla sicurezza. Sono disponibili diverse impostazioni di sicurezza che possono limitare ulteriormente l'accesso di un'applicazione all'insieme di credenziali, in modo che non possa aggiornare i segreti, ma solo leggerli.

È possibile monitorare l'accesso all'insieme di credenziali delle chiavi per assicurarsi che solo le applicazioni previste accedano all'insieme di credenziali. I log possono essere integrati di nuovo in monitoraggio di Azure, sbloccando la possibilità di impostare avvisi quando vengono rilevate condizioni impreviste.

## <a name="kubernetes"></a>Kubernetes

All'interno di Kubernetes è disponibile un servizio simile per la gestione di piccoli elementi di informazioni segrete. I segreti Kubernetes possono essere impostati tramite il tipico `kubectl` eseguibile.

La creazione di un segreto è semplice come trovare la versione Base64 dei valori da archiviare:

```console
echo -n 'admin' | base64
YWRtaW4=
echo -n '1f2d1e2e67df' | base64
MWYyZDFlMmU2N2Rm
```

Quindi, aggiungerlo a un file Secrets denominato, `secret.yml` ad esempio, simile all'esempio seguente:

```yml
apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  username: YWRtaW4=
  password: MWYyZDFlMmU2N2Rm
```

Infine, è possibile caricare il file in Kubernetes eseguendo il comando seguente:

```console
kubectl apply -f ./secret.yaml
```

Questi segreti possono quindi essere montati in volumi o esposti ai processi dei contenitori tramite le variabili di ambiente. L'approccio dell' [app a dodici fattori](https://12factor.net/) per la creazione di applicazioni suggerisce l'uso del denominatore comune più basso per trasmettere le impostazioni a un'applicazione. Le variabili di ambiente sono il denominatore comune più basso, perché sono supportate indipendentemente dal sistema operativo o dall'applicazione.

Un'alternativa all'uso dei segreti Kubernetes predefiniti è l'accesso ai segreti in Azure Key Vault dall'interno di Kubernetes. Il modo più semplice per eseguire questa operazione consiste nell'assegnare un ruolo RBAC al contenitore che desidera caricare i segreti. L'applicazione può quindi usare le API Azure Key Vault per accedere ai segreti. Tuttavia, questo approccio richiede modifiche al codice e non segue il modello di utilizzo delle variabili di ambiente. In alternativa, è possibile inserire i valori in un contenitore tramite l'uso del [Azure Key Vault iniettore](https://mrdevops.io/introducing-azure-key-vault-to-kubernetes-931f82364354). Questo approccio è in realtà più sicuro rispetto all'uso diretto dei segreti Kubernetes, in quanto è possibile accedervi dagli utenti del cluster.

## <a name="encryption-in-transit-and-at-rest"></a>Crittografia in transito e a riposo

Mantenere la sicurezza dei dati è importante se si trova su disco o in transito tra diversi servizi. Il modo più efficace per evitare la perdita di dati consiste nel crittografarlo in un formato che non può essere facilmente letto da altri utenti. Azure supporta un'ampia gamma di opzioni di crittografia.

### <a name="in-transit"></a>In transito

Esistono diversi modi per crittografare il traffico sulla rete in Azure. L'accesso ai servizi di Azure viene in genere eseguito tramite connessioni che usano Transport Layer Security (TLS). Ad esempio, tutte le connessioni alle API di Azure richiedono connessioni TLS. Analogamente, le connessioni agli endpoint in archiviazione di Azure possono essere limitate a funzionare solo su connessioni crittografate TLS.

TLS è un protocollo complesso e sa semplicemente che la connessione sta usando TLS non è sufficiente per garantire la sicurezza. Il protocollo TLS 1,0, ad esempio, non è protetto in modo cronico e TLS 1,1 non è molto migliore. Anche nelle versioni di TLS sono disponibili diverse impostazioni che possono semplificare la decrittografia delle connessioni. Il modo migliore consiste nel controllare e verificare se la connessione al server utilizza protocolli aggiornati e ben configurati.

Questo controllo può essere eseguito da un servizio esterno, ad esempio il test SSL del server SSL Labs. Un'esecuzione dei test su un tipico endpoint di Azure, in questo caso un endpoint del bus di servizio, produce un punteggio quasi perfetto di un oggetto.

Anche i servizi come i database SQL di Azure usano la crittografia TLS per nascondere i dati. La parte interessante sulla crittografia dei dati in transito con TLS è che non è possibile, neanche per Microsoft, restare in ascolto sulla connessione tra computer che eseguono TLS. Questo dovrebbe garantire la comodità per le aziende in cui i dati possono essere a rischio da Microsoft o addirittura da un attore di stato con più risorse rispetto all'utente malintenzionato standard.

![Figura 9-5 report dei Lab SSL che mostra un punteggio di un per un endpoint del bus di servizio.](./media/ssl-report.png)

**Figura 9-5**. Report di Labs SSL che mostra un punteggio di un per un endpoint del bus di servizio.

Sebbene questo livello di crittografia non sia sufficiente per tutti i tempi, dovrebbe ispirare la sicurezza che le connessioni TLS di Azure siano abbastanza sicure. Azure continuerà a evolvere gli standard di sicurezza Man mano che la crittografia migliora. È interessante tenere presente che qualcuno sta osservando gli standard di sicurezza e aggiornando Azure Man mano che migliorano.

### <a name="at-rest"></a>Inattivi

In qualsiasi applicazione sono presenti diverse posizioni in cui i dati restano su disco. Il codice dell'applicazione viene caricato da un meccanismo di archiviazione. La maggior parte delle applicazioni usa anche un tipo di database, ad esempio SQL Server, Cosmos DB o persino l'archiviazione di tabelle sorprendentemente conveniente. Tutti questi database utilizzano l'archiviazione con crittografia eccessiva per garantire che nessuno diverso dalle applicazioni con le autorizzazioni appropriate possa leggere i dati. Anche gli operatori di sistema non possono leggere i dati crittografati. Quindi, i clienti possono rimanere sicuri che le informazioni segrete rimangano segrete.

### <a name="storage"></a>Archiviazione

Il supporto di gran parte di Azure è il motore di archiviazione di Azure. I dischi delle macchine virtuali sono montati in archiviazione di Azure. I servizi Kubernetes di Azure vengono eseguiti in macchine virtuali che sono ospitate in archiviazione di Azure. Anche le tecnologie senza server, ad esempio le app funzioni di Azure e le istanze di contenitore di Azure, esauriscono il disco che fa parte di archiviazione di Azure.

Se archiviazione di Azure è ben crittografato, fornisce una base per la maggior parte degli altri elementi da crittografare. Archiviazione di Azure [è crittografato](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) con AES a [256 bit](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)conforme a [FIPS 140-2](https://en.wikipedia.org/wiki/FIPS_140) . Si tratta di una tecnologia di crittografia ben considerata che è stata l'oggetto di un controllo accademico esteso negli ultimi 20 anni. Al momento, non esiste un attacco pratico noto che consentirebbe a qualcuno senza conoscere la chiave per leggere i dati crittografati da AES.

Per impostazione predefinita, le chiavi usate per la crittografia dell'archiviazione di Azure sono gestite da Microsoft. Sono disponibili protezioni estese per impedire l'accesso dannoso a queste chiavi. Tuttavia, gli utenti con requisiti di crittografia specifici possono anche [fornire le proprie chiavi di archiviazione](https://docs.microsoft.com/azure/storage/common/storage-encryption-keys-powershell) gestite in Azure Key Vault. Queste chiavi possono essere revocate in qualsiasi momento, in modo che il rendering del contenuto dell'account di archiviazione non sia accessibile.

Le macchine virtuali usano l'archiviazione crittografata, ma è possibile fornire un altro livello di crittografia usando tecnologie come BitLocker in Windows o DM-Crypt in Linux. Queste tecnologie significano che anche se l'immagine del disco è stata persa, rimarrebbe quasi impossibile leggerla.

### <a name="azure-sql"></a>SQL di Azure

I database ospitati in SQL di Azure usano una tecnologia denominata Transparent Data Encryption (Transparent Data [Encryption)](/sql/relational-databases/security/encryption/transparent-data-encryption) per garantire la crittografia dei dati. Questa funzionalità è abilitata per impostazione predefinita in tutti i nuovi database SQL creati, ma deve essere abilitata manualmente per i database legacy. Transparent Data Encryption esegue la crittografia e la decrittografia in tempo reale di non solo del database, ma anche dei backup e dei log delle transazioni.

I parametri di crittografia vengono archiviati nel `master` database e, all'avvio, vengono letti in memoria per le operazioni rimanenti. Ciò significa che il `master` database deve rimanere non crittografato. La chiave effettiva viene gestita da Microsoft. Tuttavia, gli utenti con requisiti di sicurezza esatti possono fornire la propria chiave in Key Vault in modo analogo a quanto avviene per archiviazione di Azure. Il Key Vault fornisce servizi come la rotazione e la revoca delle chiavi.

La parte "trasparente" di TDS deriva dal fatto che non sono necessarie modifiche client per l'utilizzo di un database crittografato. Sebbene questo approccio offra una corretta sicurezza, la perdita della password del database è sufficiente per consentire agli utenti di decrittografare i dati. Esiste un altro approccio che crittografa singole colonne o tabelle in un database. [Always Encrypted](https://docs.microsoft.com/azure/sql-database/sql-database-always-encrypted-azure-key-vault) garantisce che i dati crittografati non vengano visualizzati in testo normale all'interno del database.

La configurazione di questo livello di crittografia richiede l'esecuzione di una procedura guidata in SQL Server Management Studio di selezionare il tipo di crittografia e la posizione in Key Vault per archiviare le chiavi associate.

![Figura 9-6 selezione di colonne in una tabella da crittografare con Always Encrypted](./media/always-encrypted.png)

**Figura 9-6**. Selezione di colonne in una tabella da crittografare con Always Encrypted.

Le applicazioni client che leggono le informazioni da queste colonne crittografate devono avere un limite speciale per leggere i dati crittografati. È necessario aggiornare le stringhe di connessione con `Column Encryption Setting=Enabled` e le credenziali client devono essere recuperate dal Key Vault. Il client SQL Server deve quindi essere preimpostato con le chiavi di crittografia della colonna. Al termine, le azioni rimanenti usano le interfacce standard per il client SQL. Ovvero strumenti come elegante e Entity Framework, basati sul client SQL, continueranno a funzionare senza modifiche. Always Encrypted potrebbe non essere ancora disponibile per ogni SQL Server driver in ogni lingua.

La combinazione di Transparent Data Encryption e Always Encrypted, entrambi utilizzabili con chiavi specifiche del client, garantisce che siano supportati anche i requisiti di crittografia più precisi.

### <a name="cosmos-db"></a>Cosmos DB

Cosmos DB è il database più recente fornito da Microsoft in Azure. È stato creato da zero con la sicurezza e la crittografia. La crittografia AES-256bit è standard per tutti i database Cosmos DB e non può essere disabilitata. In combinazione con il requisito TLS 1,2 per la comunicazione, viene crittografata l'intera soluzione di archiviazione.

![Figura 9-7 flusso di crittografia dei dati in Cosmos DB](./media/cosmos-encryption.png)

**Figura 9-7**. Il flusso di crittografia dei dati all'interno Cosmos DB.

Sebbene Cosmos DB non fornisca le chiavi di crittografia del cliente, il team ha svolto un lavoro significativo per assicurarsi che rimanga compatibile con PCI-DSS senza questo. Cosmos DB non supporta ancora la crittografia di una singola colonna simile al Always Encrypted di Azure SQL.

## <a name="keeping-secure"></a>Mantenimento della sicurezza

Azure dispone di tutti gli strumenti necessari per rilasciare un prodotto altamente protetto. Tuttavia, una catena è altrettanto complessa del suo collegamento più debole. Se le applicazioni distribuite in Azure non sono sviluppate con un approccio di sicurezza appropriato e controlli di sicurezza efficaci, diventano il collegamento debole nella catena. Sono disponibili molti strumenti di analisi statica, librerie di crittografia e procedure di sicurezza eccezionali che è possibile usare per garantire che il software installato in Azure sia sicuro come Azure. Gli esempi includono [strumenti di analisi statica](https://www.whitesourcesoftware.com/), [librerie di crittografia](https://www.libressl.org/)e procedure di [sicurezza](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/).

>[!div class="step-by-step"]
>[Precedente](security.md) 
> [Avanti](devops.md)
