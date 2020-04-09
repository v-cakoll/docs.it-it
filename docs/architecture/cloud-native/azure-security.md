---
title: Sicurezza di Azure per le app native nel cloudAzure security for cloud-native apps
description: Architettura delle app .NET native per Azure nel cloud Azure Security for Cloud Native Apps
ms.date: 06/30/2019
ms.openlocfilehash: 13b5ad7a883a83014913fa0a6a020610c28c524f
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989142"
---
# <a name="azure-security-for-cloud-native-apps"></a>Sicurezza di Azure per le app native nel cloudAzure security for cloud-native apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le applicazioni native nel cloud possono essere più semplici e più difficili da proteggere rispetto alle applicazioni tradizionali. Al rovescio della medaglia, è necessario proteggere le applicazioni più piccole e dedicare più energia per costruire l'infrastruttura di sicurezza. La natura eterogenea dei linguaggi e degli stili di programmazione nella maggior parte delle distribuzioni di servizi significa anche che è necessario prestare maggiore attenzione ai bollettini sulla sicurezza di molti provider diversi.

D'altra parte, i servizi più piccoli, ognuno con il proprio archivio dati, limitano l'ambito di un attacco. Se un utente malintenzionato compromette un sistema, è probabilmente più difficile per l'utente malintenzionato passare a un altro sistema rispetto a un'applicazione monolitica. I confini di processo sono forti confini. Inoltre, se un backup del database perde, il danno è più limitato, in quanto tale database contiene solo un sottoinsieme di dati ed è improbabile che contenga dati personali.

## <a name="threat-modeling"></a>Modellazione delle minacce

Non importa se i vantaggi superano gli svantaggi delle applicazioni cloud-native, la stessa mentalità di sicurezza olistica deve essere seguita. La sicurezza e il pensiero sicuro devono essere parte di ogni fase della storia dello sviluppo e delle operazioni. Quando si pianifica un'applicazione porre domande come:

- Quale sarebbe l'impatto della perdita di questi dati?
- Come possiamo limitare i danni causati da dati eromdati inseriti in questo servizio?
- Chi dovrebbe avere accesso a questi dati?
- Esistono criteri di controllo in atto intorno al processo di sviluppo e rilascio?

Tutte queste domande fanno parte di un processo chiamato [modellazione delle minacce](https://docs.microsoft.com/azure/security/azure-security-threat-modeling-tool). Questo processo cerca di rispondere alla domanda di quali minacce ci sono al sistema, quanto sono probabili le minacce sono, e il danno potenziale da loro.

Una volta che l'elenco delle minacce è stato stabilito, è necessario decidere se vale la pena di mitigare. A volte una minaccia è così improbabile e costoso per pianificare che non vale la pena spendere energia su di esso. Ad esempio, alcuni attori a livello di stato potrebbero inserire modifiche nella progettazione di un processo utilizzato da milioni di dispositivi. Ora, invece di eseguire una certa parte di codice nel [Ring 3](https://en.wikipedia.org/wiki/Protection_ring), tale codice viene eseguito nel Ring 0. Ciò consente un exploit che può bypassare l'hypervisor ed eseguire il codice di attacco sulle macchine bare metal, consentendo attacchi a tutte le macchine virtuali in esecuzione su tale hardware.

I processori alterati sono difficili da rilevare senza un microscopio e una conoscenza avanzata del design in silicio di tale processore. È improbabile che questo scenario si verifichi e costoso attenuare, quindi probabilmente nessun modello di minaccia consiglierebbe di proteggere gli exploit.

Le minacce più probabili, ad `Id` esempio i controlli `Id=2` `Id=3` di accesso interrotti che consentono attacchi di incremento (sostituendo con l'URL) o SQL injection, sono più attraenti per creare protezioni contro. Le attenuazioni per queste minacce sono abbastanza ragionevoli per costruire e prevenire imbarazzanti falle di sicurezza che spalmano la reputazione della società.

## <a name="principle-of-least-privilege"></a>Principio dei privilegi minimi

Una delle idee fondanti nella sicurezza informatica è il principio del privilegio minimo (POLP). In realtà è un'idea fondamentale nella maggior parte di qualsiasi forma di sicurezza sia digitale o fisica. In breve, il principio è che qualsiasi utente o processo dovrebbe avere il minor numero di diritti possibile per eseguire il proprio compito.

Ad esempio, pensa ai cassieri di una banca: l'accesso alla cassaforte è un'attività non comune. Quindi, il cassiere medio non può aprire la cassaforte da soli. Per ottenere l'accesso, è necessario inoltrare la richiesta tramite un responsabile bancario, che esegue ulteriori controlli di sicurezza.

In un sistema informatico, un fantastico esempio è il diritto di un utente che si connette a un database. In molti casi, è un singolo account utente utilizzato per compilare la struttura del database ed eseguire l'applicazione. Tranne in casi estremi, l'account che esegue l'applicazione non necessita della possibilità di aggiornare le informazioni sullo schema. Devono essere presenti diversi account che forniscono diversi livelli di privilegio. L'applicazione deve utilizzare solo il livello di autorizzazione che concede l'accesso in lettura e scrittura ai dati nelle tabelle. Questo tipo di protezione eliminerebbe gli attacchi che miravano a eliminare le tabelle di database o introdurre trigger dannosi.

Quasi ogni parte della creazione di un'applicazione cloud-native può trarre vantaggio dal ricordare il principio dei privilegi minimi. È possibile trovarlo in gioco durante la configurazione di firewall, gruppi di sicurezza di rete, ruoli e ambiti in controllo degli accessi in base al ruolo (RBAC).

## <a name="penetration-testing"></a>Test di penetrazione

Man mano che le applicazioni diventano più complicate, il numero di vettori di attacco aumenta a una velocità allarmante. La modellazione delle minacce è difettosa in quanto tende ad essere eseguita dalle stesse persone che creano il sistema. Nello stesso modo in cui molti sviluppatori hanno difficoltà a immaginare le interazioni con l'utente e quindi creare interfacce utente inutilizzabili, la maggior parte degli sviluppatori ha difficoltà a vedere ogni vettore di attacco. E 'anche possibile che gli sviluppatori che costruiscono il sistema non sono ben versati in metodologie di attacco e perdere qualcosa di cruciale.

Test di penetrazione o "test della penna" comporta l'inserimento di attori esterni per tentare di attaccare il sistema. Questi aggressori possono essere una società di consulenza esterna o altri sviluppatori con buone conoscenze di sicurezza da un'altra parte del business. Hanno dato carta bianca per tentare di sovvertire il sistema. Spesso, troveranno ampie falle di sicurezza che devono essere patchate. A volte il vettore di attacco sarà qualcosa di totalmente inaspettato come sfruttare un attacco di phishing contro il CEO.

Azure stesso è costantemente sottoposto ad attacchi da un [team di hacker all'interno di Microsoft](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/). Nel corso degli anni, sono stati i primi a trovare decine di vettori di attacco potenzialmente catastrofici, chiudendoli prima che possano essere sfruttati esternamente. Più un target è allettante, più è probabile che gli attori eterni tentino di sfruttarlo e ci sono alcuni obiettivi nel mondo più allettanti di Azure.

## <a name="monitoring"></a>Monitoraggio

Se un utente malintenzionato tenta di penetrare un'applicazione, dovrebbe essere presente un avviso di esso. Spesso, gli attacchi possono essere individuati esaminando i registri dai servizi. Gli attacchi lasciano segni rivelatori che possono essere individuati prima che abbiano successo. Ad esempio, un utente malintenzionato che tenta di indovinare una password effettuerà molte richieste a un sistema di accesso. Il monitoraggio intorno al sistema di login può rilevare modelli strani che sono fuori linea con il modello di accesso tipico. Questo monitoraggio può essere trasformato in un avviso che può, a sua volta, avvisare una persona operativa di attivare una sorta di contromisura. Un sistema di monitoraggio altamente maturo potrebbe anche agire in base a queste deviazioni aggiungendo in modo proattivo regole per bloccare le richieste o limitare le risposte.

## <a name="securing-the-build"></a>Protezione della compilazione

Un luogo in cui la sicurezza è spesso trascurato è intorno al processo di compilazione. Non solo la compilazione deve eseguire controlli di sicurezza, ad esempio l'analisi di codice non sicuro o credenziali archiviate, ma la compilazione stessa deve essere sicura. Se il server di compilazione è compromesso, fornisce un vettore fantastico per l'introduzione di codice arbitrario nel prodotto.

Si supponga che un utente malintenzionato sta cercando di rubare le password di persone che accede a un'applicazione web. Potrebbero introdurre un'istruzione di compilazione che modifica il codice estratto per eseguire il mirroring di qualsiasi richiesta di accesso a un altro server. La volta successiva che il codice passa attraverso la compilazione, viene aggiornato automaticamente. La scansione della vulnerabilità del codice sorgente non catturerà questo come viene eseguito prima della compilazione. Allo stesso modo, nessuno lo catturerà in una revisione del codice perché le istruzioni di compilazione risiedono nel server di compilazione. Il codice sfruttato andrà in produzione dove può raccogliere le password. Probabilmente non c'è nessun log di controllo delle modifiche del processo di compilazione, o almeno nessuno monitora il controllo.

Questo è un perfetto esempio di un target di valore apparentemente basso che può essere utilizzato per penetrare nel sistema. Una volta che un utente malintenzionato viola il perimetro del sistema, può iniziare a lavorare su come trovare modi per elevare le autorizzazioni al punto che possono causare danni reali ovunque egli desiderino.

## <a name="building-secure-code"></a>Creazione di codice sicuro

.NET Framework è già un framework abbastanza sicuro. Evita alcune delle insidie del codice non gestito, ad esempio a piedi fuori le estremità delle matrici. Il lavoro è attivamente fatto per risolvere i falli di sicurezza come vengono scoperti. C'è anche un [programma bug bounty](https://www.microsoft.com/msrc/bounty) che paga i ricercatori per trovare problemi nel quadro e segnalarli invece di sfruttarli.

Esistono molti modi per rendere il codice .NET più sicuro. Seguire le linee guida, ad esempio le linee guida di [codifica sicura per l'articolo .NET](https://docs.microsoft.com/dotnet/standard/security/secure-coding-guidelines) è un passaggio ragionevole da eseguire per garantire che il codice sia protetto da zero. La [Top 10 di OWASP](https://owasp.org/www-project-top-ten/) è un'altra guida inestimabile per creare codice sicuro.

Il processo di compilazione è un buon punto di partenza per mettere gli strumenti di scansione per rilevare i problemi nel codice sorgente prima che lo rendano in produzione. La maggior parte di ogni progetto ha dipendenze da alcuni altri pacchetti. Uno strumento in grado di eseguire la scansione di pacchetti obsoleti catturerà i problemi in una build notturna. Anche quando si creano immagini Docker, è utile verificare e assicurarsi che l'immagine di base non condisponga di vulnerabilità note. Un'altra cosa da controllare è che nessuno ha accidentalmente archiviato le credenziali.

## <a name="built-in-security"></a>Sicurezza integrata

Azure è progettato per bilanciare usabilità e sicurezza per la maggior parte degli utenti. Utenti diversi avranno requisiti di sicurezza diversi, pertanto devono ottimizzare il loro approccio alla sicurezza cloud. Microsoft pubblica una grande quantità di informazioni sulla protezione nel [Centro protezione](https://azure.microsoft.com/support/trust-center/). Questa risorsa dovrebbe essere la prima tappa per quei professionisti interessati a comprendere il funzionamento delle tecnologie di mitigazione degli attacchi incorporate.

All'interno del portale di Azure, [Azure Advisor](https://azure.microsoft.com/services/advisor/) è un sistema che analizza costantemente un ambiente e formula raccomandazioni. Alcuni di questi consigli sono progettati per risparmiare denaro agli utenti, ma altri sono progettati per identificare configurazioni potenzialmente non sicure, ad esempio avere un contenitore di archiviazione aperto al mondo e non protetto da una rete virtuale.

## <a name="azure-network-infrastructure"></a>Infrastruttura di rete di Azure

In un ambiente di distribuzione locale, una grande quantità di energia è dedicata alla configurazione della rete. Impostazione di router, switch, e questo è un lavoro complicato. Le reti consentono a determinate risorse di comunicare con altre risorse e in alcuni casi impediscono l'accesso. Una regola di rete frequente consiste nel limitare l'accesso all'ambiente di produzione dall'ambiente di sviluppo sulla possibilità che un frammento di codice semi-sviluppato esegua problemi ed elimini una parte di dati.

La maggior parte delle risorse di PaaS Azure dispone solo della configurazione di rete più semplice e permissiva. Ad esempio, chiunque su Internet può accedere a un servizio app. Le nuove istanze di SQL Server in genere sono limitate, in modo che le parti esterne non possano accedervi, ma gli intervalli di indirizzi IP usati da Azure stesso sono consentiti. Pertanto, mentre il server SQL è protetto da minacce esterne, un utente malintenzionato deve solo configurare una testa di ponte di Azure da cui è possibile avviare attacchi contro tutte le istanze SQL in Azure.So, while the SQL server is protected from external threats, an attacker only needs to set up an Azure bridgehead from where they can launch attacks against all SQL instances on Azure.

Fortunatamente, la maggior parte delle risorse di Azure può essere inserita in una rete virtuale di Azure che consente un controllo degli accessi più granulare. Analogamente al modo in cui le reti locali stabiliscono reti private protette dal resto del mondo, le reti virtuali sono isole di indirizzi IP privati che si trovano all'interno della rete di Azure.

![Figura 10-1 Una rete](./media/virtual-network.png)
virtuale in Azure**Figura 10-1**. Una rete virtuale in Azure.A virtual network in Azure.

Allo stesso modo in cui le reti locali dispongono di un firewall che disciplina l'accesso alla rete, è possibile stabilire un firewall simile al limite della rete virtuale. Per impostazione predefinita, tutte le risorse in una rete virtuale possono comunque comunicare con Internet.By default, all the resources on a virtual network can still talk to the Internet. Sono solo le connessioni in ingresso che richiedono una qualche forma di eccezione esplicita del firewall.

Una volta stabilita la rete, le risorse interne, ad esempio gli account di archiviazione, possono essere configurate in modo da consentire l'accesso solo alle risorse presenti anche nella rete virtuale. Questo firewall fornisce un ulteriore livello di sicurezza, nel caso in cui le chiavi per tale account di archiviazione vengano trapelate, gli utenti malintenzionati non sarebbero in grado di connettersi ad esso per sfruttare le chiavi trapelate. Questo è un altro esempio del principio del privilegio minimo.

I nodi in un cluster Di Azure Kubernetes possono partecipare a una rete virtuale come altre risorse più native di Azure.The nodes in an Azure Kubernetes cluster can participate in a virtual network just like other resources that are more native to Azure. Questa funzionalità è denominata interfaccia di [rete del contenitore](https://github.com/Azure/azure-container-networking/blob/master/docs/cni.md)di Azure . In effetti, alloca una subnet all'interno della rete virtuale in cui vengono allocate le macchine virtuali e le immagini del contenitore.

Continuando lungo il percorso per illustrare il principio dei privilegi minimi, non tutte le risorse all'interno di una rete virtuale devono comunicare con ogni altra risorsa. Ad esempio, in un'applicazione che fornisce un'API Web su un account di archiviazione e un database SQL, è improbabile che il database e l'account di archiviazione debbano comunicare tra loro. Qualsiasi condivisione dei dati tra di loro passerebbe attraverso l'applicazione web. Pertanto, un gruppo di sicurezza di [rete (NSG)](https://docs.microsoft.com/azure/virtual-network/security-overview) potrebbe essere utilizzato per negare il traffico tra i due servizi.

Un criterio di negazione della comunicazione tra le risorse può essere fastidioso da implementare, soprattutto proveniente da uno sfondo di utilizzo di Azure senza restrizioni sul traffico. In alcuni altri cloud, il concetto di gruppi di sicurezza di rete è molto più diffuso. Ad esempio, il criterio predefinito in AWS è che le risorse non possono comunicare tra loro fino a quando non vengono abilitate dalle regole in un gruppo di sicurezza di rete. Anche se più lento per sviluppare questo, ambiente più restrittivo fornisce un'impostazione predefinita più sicura. L'uso delle procedure DevOps appropriate, in particolare l'uso di [Azure Resource Manager o Terraform](infrastructure-as-code.md) per gestire le autorizzazioni può semplificare il controllo delle regole.

Le reti virtuali possono essere utili anche quando si configurano le comunicazioni tra le risorse locali e cloud. Una rete privata virtuale può essere utilizzata per collegare senza problemi le due reti. Ciò consente l'esecuzione di una rete virtuale senza alcun tipo di gateway per gli scenari in cui tutti gli utenti sono in loco. Ci sono una serie di tecnologie che possono essere utilizzate per stabilire questa rete. Il più semplice consiste nell'usare una VPN da sito a sito che può essere stabilita tra molti router e Azure.The simplest is to use a [site-to-site VPN](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#s2smulti) that can be established between many routers and Azure. Il traffico viene crittografato e sottoposto a tunneling su Internet allo stesso costo per byte di qualsiasi altro traffico. Per gli scenari in cui è auspicabile una maggiore larghezza di banda o una maggiore sicurezza, Azure offre un servizio denominato Express Route che usa un circuito privato tra una rete locale e Azure.For scenarios where more bandwidth or more security is desirable, Azure offers a service called [Express Route](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#ExpressRoute) that uses a private circuit between an on-premises network and Azure. È più costoso e difficile da stabilire, ma anche più sicuro.

## <a name="role-based-access-control-for-restricting-access-to-azure-resources"></a>Controllo degli accessi in base al ruolo per limitare l'accesso alle risorse di AzureRole-based access control for restricting access to Azure resources

Il controllo degli accessi in base al ruolo è un sistema che fornisce un'identità alle applicazioni in esecuzione in Azure.RBAC is a system that provides an identity to applications running in Azure. Le applicazioni possono accedere alle risorse usando questa identità anziché o in aggiunta all'uso di chiavi o password.

## <a name="security-principals"></a>Entità di sicurezza

Il primo componente in RBAC è un'entità di sicurezza. Un'entità di sicurezza può essere un utente, un gruppo, un'entità servizio o un'identità gestita.

![Figura 10-2 Diversi tipi](./media/rbac-security-principal.png)
di entità di sicurezza**Figura 10-2**. Diversi tipi di entità di sicurezza.

- Utente: qualsiasi utente che dispone di un account in Azure Active Directory è un utente.
- Gruppo: raccolta di utenti da Azure Active Directory.Group - A collection of users from Azure Active Directory. Come membro di un gruppo, un utente assume i ruoli di tale gruppo oltre al proprio.
- Entità servizio: identità di sicurezza con cui vengono eseguiti servizi o applicazioni.
- Managed identity - An Azure Active Directory identity managed by Azure. Le identità gestite vengono in genere usate quando si sviluppano applicazioni cloud che gestiscono le credenziali per l'autenticazione ai servizi di Azure.Managed identities are typically used when developing cloud applications that manage the credentials for authenticating to Azure services.

L'entità di sicurezza può essere applicata alla maggior parte di tutte le risorse. Ciò significa che è possibile assegnare un'entità di sicurezza a un contenitore in esecuzione all'interno di Azure Kubernetes, consentendo gli accessi ai segreti archiviati in Key Vault. Una funzione di Azure potrebbe assumere un'autorizzazione che consente di comunicare con un'istanza di Active Directory per convalidare un token JWT per un utente chiamante. Una volta abilitati i servizi con un'entità servizio, le relative autorizzazioni possono essere gestite in modo granulare usando ruoli e ambiti.

## <a name="roles"></a>Ruoli

Un'entità di sicurezza può assumere molti ruoli o, usando un'analogia più sartoriale, indossare molti cappelli. Ogni ruolo definisce una serie di autorizzazioni, ad esempio "Lettura di messaggi dall'endpoint del bus di servizio di Azure". Il set di autorizzazioni effettivo di un'entità di sicurezza è la combinazione di tutte le autorizzazioni assegnate a tutti i ruoli di cui dispone l'entità di sicurezza. Azure ha un numero elevato di ruoli predefiniti e gli utenti possono definire i propri ruoli.

![Figura 10-3 Definizioni](./media/rbac-role-definition.png)
di ruolo RBAC Figura**10-3**. Definizioni dei ruoli RBAC.

Integrato in Azure sono anche una serie di ruoli di alto livello, ad esempio proprietario, collaboratore, lettore e amministratore dell'account utente. Con il ruolo Proprietario, un'entità di sicurezza può accedere a tutte le risorse e assegnare autorizzazioni ad altri utenti. Un collaboratore ha lo stesso livello di accesso a tutte le risorse, ma non può assegnare autorizzazioni. Un lettore può visualizzare solo le risorse di Azure esistenti e un amministratore dell'account utente può gestire l'accesso alle risorse di Azure.A Reader can only view existing Azure resources and a User Account Administrator can manage access to Azure resources.

Ruoli predefiniti più granulari, ad esempio I diritti [di collaboratore della zona DNS](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles#dns-zone-contributor) sono limitati a un singolo servizio. Le entità di sicurezza possono assumere un numero qualsiasi di ruoli.

## <a name="scopes"></a>Ambiti

I ruoli possono essere applicati a un set limitato di risorse all'interno di Azure.Roles can be applied to a restricted set of resources within Azure. Ad esempio, applicando l'ambito all'esempio precedente di lettura da una coda del bus di servizio, `blah.servicebus.windows.net/queue1`è possibile limitare l'autorizzazione a una singola coda: "Leggere i messaggi dall'endpoint del bus di servizio di Azure"For example, applying scope to the previous example of reading from a Service Bus queue, you can narrow the permission to a single queue: "Read messages from Azure Service Bus endpoint"

L'ambito può essere limitato come una singola risorsa o può essere applicato a un intero gruppo di risorse, sottoscrizione o anche gruppo di gestione.

Quando si esegue il test se un'entità di sicurezza dispone di una determinata autorizzazione, viene presa in considerazione la combinazione di ruolo e ambito. Questa combinazione fornisce un potente meccanismo di autorizzazione.

## <a name="deny"></a>Nega

In precedenza, solo le regole "consenti" erano consentite per il controllo degli accessi in base al ruolo. Questo comportamento ha reso alcuni ambiti complicati da compilare. Ad esempio, consentire a un'entità di sicurezza l'accesso a tutti gli account di archiviazione, ad eccezione di uno necessario concedere l'autorizzazione esplicita a un elenco potenzialmente infinito di account di archiviazione. Ogni volta che viene creato un nuovo account di archiviazione, è necessario aggiungerlo a questo elenco di account. Questo sovraccarico di gestione aggiunto che certamente non era auspicabile.

Le regole di negazione hanno la precedenza sulle regole di autorizzazione. Ora rappresenta lo stesso ambito "consenti tutti tranne uno" potrebbe essere rappresentato come due regole "consenti tutti" e "nega questo specifico". Negare le regole non solo facilita la gestione, ma consente risorse che sono più sicure negando l'accesso a tutti.

## <a name="checking-access"></a>Controllo dell'accesso

Come si può immaginare, avere un numero elevato di ruoli e ambiti può rendere difficile trovare l'autorizzazione efficace di un'entità servizio. Piling regole di negazione su questo, serve solo ad aumentare la complessità. Fortunatamente, c'è un calcolatore di autorizzazioni che può mostrare le autorizzazioni valide per qualsiasi entità servizio. In genere si trova nella scheda IAM nel portale, come illustrato nella Figura 10-3.

![Figura 10-4 Calcolatore di](./media/check-rbac.png)
autorizzazioni per un servizio app**Figura 10-4**. Calcolatore delle autorizzazioni per un servizio app.

## <a name="securing-secrets"></a>Protezione dei segreti

Le password e i certificati sono un vettore di attacco comune per gli utenti malintenzionati. Hardware password-cracking può fare un attacco di forza bruta e cercare di indovinare miliardi di password al secondo. Quindi è importante che le password utilizzate per accedere alle risorse siano complesse, con una grande varietà di caratteri. Queste password sono esattamente il tipo di password che sono quasi impossibili da ricordare. Fortunatamente, le password in Azure in realtà non hanno bisogno di essere conosciute da qualsiasi essere umano.

Molti esperti di sicurezza [suggeriscono](https://www.troyhunt.com/password-managers-dont-have-to-be-perfect-they-just-have-to-be-better-than-not-having-one/) che l'utilizzo di un gestore di password per mantenere le proprie password è l'approccio migliore. Anche se centralizza le tue password in un'unica posizione, consente anche di utilizzare password altamente complesse e di garantire che siano uniche per ogni account. Lo stesso sistema esiste all'interno di Azure: un archivio centrale per i segreti.

## <a name="azure-key-vault"></a>Insieme di credenziali chiave di Azure

Archiviazione delle chiavi di Azure offre una posizione centralizzata per archiviare le password per database, chiavi API e certificati. Una volta che un segreto viene inserito nel Vault, non viene mai più mostrato e i comandi per estrarlo e visualizzarlo sono volutamente complicati. Le informazioni nella cassaforte sono protette tramite crittografia software o moduli di sicurezza hardware convalidati FIPS 140-2 Livello 2.

L'accesso all'insieme di credenziali delle chiavi viene fornito tramite RBC, il che significa che non un solo utente può accedere alle informazioni nell'insieme di credenziali. Pronunciare un'applicazione Web che desidera accedere alla stringa di connessione al database archiviata nell'insieme di credenziali delle chiavi di Azure.Say a web application wishes to access the database connection string stored in Azure Key Vault. Per ottenere l'accesso, le applicazioni devono essere eseguite usando un'entità servizio. In questo ruolo presunto, possono leggere i segreti dalla cassaforte. Esistono diverse impostazioni di sicurezza che possono limitare ulteriormente l'accesso di un'applicazione all'insieme di credenziali, in modo che non possa aggiornare i segreti ma solo leggerli.

L'accesso all'insieme di credenziali delle chiavi può essere monitorato per garantire che solo le applicazioni previste accedano all'insieme di credenziali. I log possono essere integrati in Monitoraggio di Azure, sbloccando la possibilità di configurare avvisi quando si verificano condizioni impreviste.

## <a name="kubernetes"></a>Kubernetes

All'interno di Kubernetes, c'è un servizio simile per mantenere piccoli pezzi di informazioni segrete. Kubernetes Secrets può essere `kubectl` impostato tramite il tipico eseguibile.

Creare un segreto è semplice come trovare la versione base64 dei valori da memorizzare:

```console
echo -n 'admin' | base64
YWRtaW4=
echo -n '1f2d1e2e67df' | base64
MWYyZDFlMmU2N2Rm
```

Quindi aggiungendolo a un `secret.yml` file di segreti denominato per esempio simile all'esempio seguente:Then adding it to a secrets file named for example that looks similar to the following example:

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

Infine, questo file può essere caricato in Kubernetes eseguendo il seguente comando:

```console
kubectl apply -f ./secret.yaml
```

Questi segreti possono quindi essere montati in volumi o esposti ai processi contenitore tramite variabili di ambiente. L'approccio [dell'app](https://12factor.net/) a dodici fattori per la creazione di applicazioni suggerisce l'utilizzo del minimo comune denominatore per trasmettere le impostazioni a un'applicazione. Le variabili di ambiente sono il minimo comune denominatore, perché sono supportate indipendentemente dal sistema operativo o dall'applicazione.

Un'alternativa per usare i segreti Kubernetes incorporati consiste nell'accedere ai segreti in Azure Key Vault dall'interno di Kubernetes.An alternative to use the built-in Kubernetes secrets is to access the secrets in Azure Key Vault from within Kubernetes. Il modo più semplice per eseguire questa operazione consiste nell'assegnare un ruolo RBAC al contenitore che desidera caricare i segreti. L'applicazione può quindi usare le API dell'insieme di chiavi di Azure per accedere ai segreti. Tuttavia, questo approccio richiede modifiche al codice e non segue il modello di utilizzo delle variabili di ambiente. Al contrario, è possibile inserire valori in un contenitore tramite l'uso [dell'iniettore dell'insieme di credenziali delle](https://mrdevops.io/introducing-azure-key-vault-to-kubernetes-931f82364354)chiavi di Azure . Questo approccio è in realtà più sicuro rispetto all'utilizzo diretto dei segreti Kubernetes, in quanto è possibile accedervi dagli utenti del cluster.

## <a name="encryption-in-transit-and-at-rest"></a>Crittografia in transito e inattivi

Mantenere i dati al sicuro è importante sia che si tratti di disco o di transito tra vari servizi diversi. Il modo più efficace per evitare che i dati perdano è quello di crittografarli in un formato che non può essere letto facilmente da altri. Azure supporta un'ampia gamma di opzioni di crittografia.

### <a name="in-transit"></a>In transito

Esistono diversi modi per crittografare il traffico nella rete in Azure.There are several ways to encrypt traffic on the network in Azure. L'accesso ai servizi di Azure viene in genere eseguito tramite connessioni che usano Transport Layer Security (TLS). Ad esempio, tutte le connessioni alle API di Azure richiedono connessioni TLS. Allo stesso modo, le connessioni agli endpoint nell'archiviazione di Azure possono essere limitate per funzionare solo tramite connessioni crittografate TLS.

TLS è un protocollo complicato e semplicemente sapendo che la connessione utilizza TLS non è sufficiente per garantire la sicurezza. Ad esempio, TLS 1.0 è cronicamente insicuro e TLS 1.1 non è molto migliore. Anche all'interno delle versioni di TLS, ci sono varie impostazioni che possono rendere le connessioni più facili da decifrare. La migliore linea d'azione è controllare e vedere se la connessione al server utilizza protocolli aggiornati e ben configurati.

Questo controllo può essere eseguito da un servizio esterno, ad esempio SSL labs' Server Test. A test run against a typical Azure endpoint, in this case a service bus endpoint, yields a near perfect score of A.

Anche i servizi come i database SQL di Azure usano la crittografia TLS per mantenere nascosti i dati. La parte interessante della crittografia dei dati in transito tramite TLS è che non è possibile, anche per Microsoft, rimanere in ascolto sulla connessione tra computer che eseguono TLS. Questo dovrebbe fornire conforto per le aziende interessate che i loro dati possono essere a rischio da Microsoft corretto o anche un attore di stato con più risorse rispetto all'attaccante standard.

![Figura 10-5 Report di laboratori SSL che mostra un punteggio di A per un endpoint del bus di servizio. ](./media/ssl-report.png)
 **Figura 10-5**. Report laboratori SSL che mostrano un punteggio di A per un endpoint del bus di servizio.

Anche se questo livello di crittografia non sarà sufficiente per tutto il tempo, dovrebbe ispirare fiducia che le connessioni TLS di Azure siano abbastanza sicure. Azure continuerà a evolvere i propri standard di sicurezza man mano che la crittografia migliora. È bello sapere che c'è qualcuno che guarda gli standard di sicurezza e aggiorna Azure man mano che migliorano.

### <a name="at-rest"></a>Inattivi

In qualsiasi applicazione, ci sono un certo numero di posizioni in cui i dati poggiano su disco. Il codice dell'applicazione stesso viene caricato da un meccanismo di archiviazione. La maggior parte delle applicazioni utilizza anche un qualche tipo di database, ad esempio SQL Server, Cosmos DB o anche l'archiviazione tabelle incredibilmente efficiente in termini di prezzo. Tutti questi database utilizzano archiviazione crittografata pesantemente per garantire che nessuno diverso dalle applicazioni con le autorizzazioni appropriate possa leggere i dati. Anche gli operatori di sistema non possono leggere i dati che sono stati crittografati. Così i clienti possono rimanere sicuri che le loro informazioni segrete rimangano segrete.

### <a name="storage"></a>Archiviazione

La base di gran parte di Azure è il motore di Archiviazione di Azure.The underpinning of much of Azure is the Azure Storage engine. I dischi delle macchine virtuali sono montati in Access di Azure.Virtual machine disks are mounted on top of Azure Storage. Azure Kubernetes Services run on virtual machines that, themselves, are hosted on Azure Storage. Anche le tecnologie senza server, ad esempio le app per le funzioni di Azure e le istanze del contenitore di Azure, esauriscono il disco che fa parte di Archiviazione di Azure.Even serverless technologies, such as Azure Functions Apps and Azure Container Instances, e-out of disk that is part of Azure Storage.

Se Archiviazione di Azure è ben crittografata, fornisce anche una base per la maggior parte di tutto il resto da crittografare. Archiviazione di Azure [è crittografata](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) con [AES a 256 bit](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)conforme a [FIPS 140-2.](https://en.wikipedia.org/wiki/FIPS_140) Questa è una tecnologia di crittografia ben considerata essendo stata oggetto di un ampio esame accademico negli ultimi 20 anni o giù di lì. Al momento, non c'è nessun attacco pratico noto che consentirebbe a qualcuno senza conoscere la chiave per leggere i dati crittografati da AES.

By default, the keys used for encrypting Azure Storage are managed by Microsoft. Ci sono ampie protezioni in atto per garantire per impedire l'accesso dannoso a queste chiavi. Tuttavia, gli utenti con particolari requisiti di crittografia possono anche fornire le proprie chiavi di archiviazione gestite in Archiviazione delle chiavi di Azure.However, users with particular encryption requirements can also [provide their own storage keys](https://docs.microsoft.com/azure/storage/common/storage-encryption-keys-powershell) that are managed in Azure Key Vault. Queste chiavi possono essere revocate in qualsiasi momento, il che renderebbe inaccessibile il contenuto dell'account di archiviazione.

Le macchine virtuali usano l'archiviazione crittografata, ma è possibile fornire un altro livello di crittografia utilizzando tecnologie come BitLocker in Windows o DM-Crypt su Linux. Queste tecnologie significano che anche se l'immagine del disco fosse trapelata dall'archiviazione, rimarrebbe quasi impossibile leggerla.

### <a name="azure-sql"></a>SQL di Azure

I database ospitati in SQL di Azure usano una tecnologia denominata [Transparent Data Encryption (TDE)](/sql/relational-databases/security/encryption/transparent-data-encryption) per garantire che i dati rimangano crittografati. È abilitato per impostazione predefinita in tutti i database SQL appena creati, ma deve essere abilitato manualmente per i database legacy. TDE esegue la crittografia e la decrittografia in tempo reale non solo del database, ma anche dei backup e dei registri delle transazioni.

I parametri di crittografia `master` vengono archiviati nel database e, all'avvio, vengono letti in memoria per le operazioni rimanenti. Ciò significa `master` che il database deve rimanere non crittografato. La chiave effettiva è gestita da Microsoft.The actual key is managed by Microsoft. Tuttavia, gli utenti con requisiti di sicurezza rigorosi possono fornire la propria chiave nell'insieme di credenziali delle chiavi in modo molto simile a quello di Archiviazione di Azure.However, users with exacting security requirements may provide their own key in Key Vault in much the same way as is done for Azure Storage. L'insieme di credenziali delle chiavi fornisce servizi quali la rotazione delle chiavi e la revoca.

La parte "trasparente" di TDS deriva dal fatto che non sono necessarie modifiche client per utilizzare un database crittografato. Anche se questo approccio garantisce una buona sicurezza, la perdita della password del database è sufficiente per consentire agli utenti di decrittografare i dati. È disponibile un altro approccio che consente di crittografare singole colonne o tabelle in un database. [Always Encrypted](https://docs.microsoft.com/azure/sql-database/sql-database-always-encrypted-azure-key-vault) assicura che in nessun punto i dati crittografati vengano visualizzati in testo normale all'interno del database.

Per configurare questo livello di crittografia è necessario eseguire una procedura guidata in SQL Server Management StudioSQL Server Management Studio per selezionare il tipo di crittografia e in archivio chiavi in cui archiviare le chiavi associate.

![Figura 10-6 Selezione di colonne in una tabella](./media/always-encrypted.png)
da crittografare utilizzando Always Encrypted**Figure 10-6**. Selezione delle colonne in una tabella da crittografare tramite Always Encrypted.

Le applicazioni client che leggono informazioni da queste colonne crittografate devono eseguire particolari concessioni per leggere i dati crittografati. Le stringhe di connessione `Column Encryption Setting=Enabled` devono essere aggiornate e le credenziali client devono essere recuperate dall'insieme di credenziali delle chiavi. Il client SQL Server deve quindi essere utilizzato con le chiavi di crittografia della colonna. Una volta fatto questo, le azioni rimanenti utilizzano le interfacce standard di SQL Client. In altri modo, strumenti come Dapper ed Entity Framework, che si basano su SQL Client, continueranno a funzionare senza modifiche. Always Encrypted potrebbe non essere ancora disponibile per ogni driver di SQL Server in ogni lingua.

La combinazione di TDE e Always Encrypted, entrambi i quali possono essere utilizzati con chiavi specifiche del client, assicura che anche i requisiti di crittografia più esigenti sono supportati.

### <a name="cosmos-db"></a>Cosmos DB

Cosmos DB è il database più recente fornito da Microsoft in Azure. E 'stato costruito da zero con la sicurezza e la crittografia in mente. La crittografia AES-256bit è standard per tutti i database Cosmos DB e non può essere disabilitata. Accoppiato con il requisito TLS 1.2 per la comunicazione, l'intera soluzione di archiviazione è crittografata.

![Figura 10-7 Flusso di crittografia dei](./media/cosmos-encryption.png)
dati all'interno di Cosmos DB**Figura 10-7**. Flusso di crittografia dei dati all'interno di Cosmos DB.

Mentre Cosmos DB non fornisce per la fornitura di chiavi di crittografia dei clienti, c'è stato un lavoro significativo fatto dal team per garantire che rimanga compatibile CON PCI-DSS senza che. Cosmos DB inoltre non supporta alcun tipo di crittografia a colonna singola simile a Always Encrypted di Azure SQL.

## <a name="keeping-secure"></a>Garantire la sicurezza

Azure dispone di tutti gli strumenti necessari per rilasciare un prodotto altamente sicuro. Tuttavia, una catena è forte solo quanto il suo anello più debole. Se le applicazioni distribuite in Azure non vengono sviluppate con una mentalità di sicurezza appropriata e controlli di sicurezza corretti, diventano l'anello debole della catena. Esistono molti ottimi strumenti di analisi statica, librerie di crittografia e procedure di sicurezza che possono essere usate per garantire che il software installato in Azure sia sicuro come Azure stesso. Gli esempi includono strumenti di [analisi statica,](https://www.whitesourcesoftware.com/) [librerie](https://www.libressl.org/)di crittografia e procedure di [protezione](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/).

>[!div class="step-by-step"]
>[Successivo](security.md)
>[precedente](devops.md)
