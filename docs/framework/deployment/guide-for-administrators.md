---
title: Guida alla distribuzione di .NET Framework per amministratori
description: Leggere la guida alla distribuzione di .NET per gli amministratori. Usare queste informazioni per distribuire .NET versione 4,5 e le relative dipendenze di sistema in una rete.
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: d58eac4f21e4f1069ac392aacb4e9818831e914c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622653"
---
# <a name="net-framework-deployment-guide-for-administrators"></a>Guida alla distribuzione di .NET Framework per amministratori

Questo articolo dettagliato descrive come un amministratore di sistema può distribuire il .NET Framework 4,5 e le relative dipendenze di sistema attraverso una rete usando Microsoft endpoint Configuration Manager. L'articolo presuppone che tutti i computer client di destinazione soddisfino i requisiti minimi per .NET Framework. Per un elenco dei requisiti software e hardware per l'installazione di .NET Framework 4.5, vedere [Requisiti di sistema](../get-started/system-requirements.md).

> [!NOTE]
> Il software a cui si fa riferimento nel presente documento, inclusi, a titolo esemplificativo, i .NET Framework 4,5, Configuration Manager e Active Directory, sono soggetti a condizioni di licenza. Queste istruzioni presuppongono che tali condizioni di licenza siano state riviste e accettate dai licenziatari del software e non derogano ad alcuna condizione di tali contratti di licenza.
>
> Per informazioni sul supporto per la .NET Framework, vedere [.NET Framework i criteri di supporto ufficiale](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) nel sito web di supporto tecnico Microsoft.

In questo argomento sono incluse le sezioni seguenti:

- [Processo di distribuzione](#the_deployment_process)
- [Distribuzione di .NET Framework](#deploying_in_a_test_environment)
- [Creare una raccolta](#creating_a_collection)
- [Creare un pacchetto e un programma](#creating_a_package)
- [Selezionare un punto di distribuzione](#select_dist_point)
- [Distribuire il pacchetto](#deploying_package)
- [Risorse](#resources)
- [Risoluzione dei problemi](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a>Processo di distribuzione

Quando si dispone dell'infrastruttura di supporto sul posto, è possibile utilizzare Configuration Manager per distribuire il pacchetto ridistribuibile di .NET Framework nei computer della rete. La creazione dell'infrastruttura include la creazione e la definizione di cinque aree primarie: raccolte, un pacchetto e un programma per il software, punti di distribuzione e distribuzioni.

- Le **raccolte** sono gruppi di risorse di Configuration Manager, ad esempio utenti, gruppi di utenti o computer, ai quali viene distribuito .NET Framework. Per ulteriori informazioni, vedere [Introduzione alle raccolte in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) nella libreria della documentazione di Configuration Manager.

- I **pacchetti e programmi** in genere rappresentano le applicazioni software da installare in un computer client, ma possono anche contenere singoli file, aggiornamenti o persino singoli comandi. Per ulteriori informazioni, vedere [pacchetti e programmi in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) nella libreria della documentazione di Configuration Manager.

- I **punti di distribuzione** sono ruoli di sistema dei siti di Configuration Manager nei quali sono archiviati i file necessari per l'esecuzione del software nei computer client. Quando il client di Configuration Manager riceve ed elabora una distribuzione software, contatta un punto di distribuzione per scaricare il contenuto associato al software e avviare il processo di installazione. Per altre informazioni, vedere [Concetti di base della gestione dei contenuti in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) nella raccolta di documentazione di Configuration Manager.

- Le **distribuzioni** indicano ai membri validi della raccolta di destinazione specificata di installare il pacchetto software.

> [!IMPORTANT]
> Le procedure descritte in questo argomento includono impostazioni standard per creare e distribuire un pacchetto e un programma e potrebbero non illustrare tutte le impostazioni possibili. Per altre informazioni sulle opzioni di distribuzione di Configuration Manager, vedere [Libreria della documentazione di Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-the-net-framework"></a>Distribuzione di .NET Framework

È possibile usare Configuration Manager per distribuire un'installazione invisibile all'utente del .NET Framework 4,5, in cui gli utenti non interagiscono con il processo di installazione. A tale scopo, seguire questa procedura:

1. [Creare una raccolta](#creating_a_collection).

2. [Creare un pacchetto e un programma per il pacchetto ridistribuibile di .NET Framework](#creating_a_package).

3. [Selezionare un punto di distribuzione](#select_dist_point).

4. [Distribuire il pacchetto](#deploying_package).

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a>Creare una raccolta

In questo passaggio selezionare i computer in cui verrà distribuito il pacchetto e il programma e raggrupparli in una raccolta dispositivi. Per creare una raccolta in Configuration Manager, è possibile usare le regole di appartenenza dirette (dove vengono specificati manualmente i membri della raccolta) oppure regole di query (dove Configuration Manager determina i membri della raccolta in base ai criteri specificati). Per ulteriori informazioni sulle regole di appartenenza, incluse query e regole dirette, vedere [Introduzione alle raccolte in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) nella libreria della documentazione di Configuration Manager.

Per creare una raccolta:

1. Nella console di Configuration Manager scegliere **Asset e conformità**.

2. Nell'area di lavoro **Asset e conformità** scegliere **Raccolte dispositivi**.

3. Nella scheda **Home** del gruppo **Crea** scegliere **Crea raccolta dispositivi**.

4. Nella pagina **Generale** della **Creazione guidata raccolta dispositivi** digitare un nome per la raccolta.

5. Scegliere **Sfoglia** per specificare una raccolta di limitazione.

6. Nella pagina**Regole di appartenenza** scegliere **Aggiungi regola** e quindi **Regola diretta** per aprire la **Creazione guidata regola di appartenenza diretta**. Scegliere **Avanti**.

7. Nella pagina **Cerca risorse** scegliere **Risorsa di sistema** nell'elenco **Classe di risorse**. Nell'elenco **Nome attributo** scegliere **Nome**. Nel campo **Valore** immettere `%`, quindi scegliere **Avanti**.

8. Nella pagina **Seleziona risorse** selezionare la casella di controllo per ogni computer a cui si vuole distribuire .NET Framework. Scegliere **Avanti** e completare la procedura guidata.

9. Nella pagina **Regole di appartenenza** della **Creazione guidata raccolta dispositivi** scegliere **Avanti** e completare la procedura guidata.

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a>Creare un pacchetto e un programma per il pacchetto ridistribuibile di .NET Framework

Nei passaggi riportati di seguito viene creato manualmente un pacchetto per il pacchetto ridistribuibile di .NET Framework. Il pacchetto contiene i parametri specificati per l'installazione di .NET Framework e il percorso dal quale il pacchetto verrà distribuito ai computer di destinazione.

Per creare un pacchetto:

1. Nella console di Configuration Manager scegliere **Raccolta software**.

2. Nell'area di lavoro **Raccolta software** espandere **Gestione applicazioni** e scegliere **Pacchetti**.

3. Nella scheda **Home** scegliere **Crea pacchetto** del gruppo **Crea**.

4. Nella pagina **Pacchetto** della **Creazione guidata pacchetto e programma** immettere le informazioni seguenti:

    - Nome: `.NET Framework 4.5`

    - Produttore: `Microsoft`

    - Lingua. `English (US)`

5. Scegliere **Questo pacchetto contiene file di origine**, quindi **Sfoglia** per selezionare la cartella locale o di rete che contiene i file di installazione di .NET Framework. Dopo aver selezionato la cartella, scegliere **OK**, quindi **Avanti**.

6. Nella pagina **Tipo di programma** della procedura guidata, scegliere **Programma standard**, quindi **Avanti**.

7. Nella pagina **Programma** della **Creazione guidata pacchetto e programma** immettere le informazioni seguenti:

    1. **Nome:**`.NET Framework 4.5`

    2. **Riga di comando:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (le opzioni della riga di comando sono descritte nella tabella che segue questi passaggi)

    3. **Esegui:** Scegliere **Nascosto**.

    4. **Requisiti per esecuzione programma:** scegliere l'opzione che specifica che il programma può essere eseguito indipendentemente dal fatto che un utente sia connesso o meno.

8. Nella pagina **Requisiti** scegliere **Avanti** per accettare i valori predefiniti, quindi completare la procedura guidata.

Nella tabella seguente vengono descritte le opzioni della riga di comando specificate nel passaggio 7.

|Opzione|Descrizione|
|------------|-----------------|
|**/q**|Imposta la modalità non interattiva. Nessun input utente viene richiesto e nessun output viene visualizzato.|
|**/norestart**|Impedisce il riavvio automatico del programma di installazione. Se si usa questa opzione, il riavvio del computer deve essere gestito da Configuration Manager.|
|**/chainingpackage** *NomePacchetto*|Specifica il nome del pacchetto che esegue il concatenamento. Questa informazione viene riportata insieme alle altre informazioni sulla sessione di installazione per coloro sono registrati in Microsoft Analisi utilizzo software (CEIP). Se il nome del pacchetto include spazi, usare le virgolette doppie come delimitatori, ad esempio: **/chainingpackage "Applicazione di concatenamento"**.|

Questi passaggi creano un pacchetto denominato .NET Framework 4.5. Viene distribuita automaticamente un'installazione invisibile all'utente di .NET Framework 4.5. In un'installazione invisibile, gli utenti non interagiscono con il processo d'installazione e l'applicazione di concatenamento deve acquisire il codice restituito e gestire il riavvio. Vedere [Getting Progress Information from an Installation Package](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)) (Ottenere informazioni di stato da un pacchetto di installazione).

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a>Selezionare un punto di distribuzione

Per distribuire il pacchetto e il programma da un server ai computer client, è innanzitutto necessario specificare un sistema di siti come punto di distribuzione e distribuire il pacchetto al punto di distribuzione.

Usare i passaggi seguenti per selezionare un punto di distribuzione per il pacchetto di .NET Framework 4.5 creato nella sezione precedente:

1. Nella console di Configuration Manager scegliere **Raccolta software**.

2. Nell'area di lavoro **Raccolta software** espandere **Gestione applicazioni** e scegliere **Pacchetti**.

3. Dall'elenco di pacchetti, selezionare il pacchetto **.NET Framework 4.5** creato nella sezione precedente.

4. Nella scheda **Home** scegliere **Distribuisci contenuto** nel gruppo **Distribuzione**.

5. Nella scheda **Generale** della **Distribuzione guidata contenuto** scegliere **Avanti**.

6. Nella pagina **Destinazione contenuto** della procedura guidata scegliere **Aggiungi**, quindi **Punto di distribuzione**.

7. Nella finestra di dialogo **Aggiungi punti di distribuzione** selezionare i punti di distribuzione che ospiteranno il pacchetto e il programma, quindi scegliere **OK**.

8. Completare la procedura guidata.

Il pacchetto contiene tutte le informazioni necessarie per distribuire automaticamente .NET Framework 4.5. Prima di distribuire il pacchetto e il programma, verificare che sia stato installato nel punto di distribuzione. vedere la sezione "monitoraggio dello stato dei contenuti" di [monitorare il contenuto distribuito con Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) nella libreria della documentazione di Configuration Manager.

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a>Distribuire il pacchetto

Per distribuire il pacchetto e il programma di .NET Framework 4.5:

1. Nella console di Configuration Manager scegliere **Raccolta software**.

2. Nell'area di lavoro **Raccolta software** espandere **Gestione applicazioni** e scegliere **Pacchetti**.

3. Nell'elenco di pacchetti selezionare il pacchetto creato denominato **.NET Framework 4.5**.

4. Nella scheda **Home** scegliere **Distribuisci** del gruppo **Distribuzione**.

5. Nella pagina **Generale** della **Distribuzione guidata del software** scegliere **Sfoglia** e selezionare la raccolta creata precedentemente. Scegliere **Avanti**.

6. Nella pagina **Contenuto** della procedura guidata, verificare che il punto da cui si vuole distribuire il software sia visualizzato, quindi scegliere **Avanti**.

7. Nella pagina**Impostazioni di distribuzione** della procedura guidata, verificare che **Azione** sia impostato su **Installa** e **Scopo** su **Obbligatorio**. Ciò garantisce che l'installazione del pacchetto software sarà obbligatoria sui computer di destinazione. Scegliere **Avanti**.

8. Nella pagina **Pianificazione** della procedura guidata specificare quando si vuole installare .NET Framework. È possibile scegliere **Nuovo** per definire una data e un orario di installazione, specificare che il software dovrà essere installato quando l'utente accede o si disconnette oppure non appena possibile. Scegliere **Avanti**.

9. Nella pagina **Esperienza utente** della procedura guidata, usare i valori predefiniti e scegliere **Avanti**.

    > [!WARNING]
    > Nell'ambiente di produzione potrebbero essere impostati criteri che richiedono selezioni diverse per la pianificazione dell'assegnazione. Per informazioni su queste opzioni, vedere [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29) (Proprietà dei nomi degli annunci: scheda Pianificazione).

10. Nella pagina di **Punti di distribuzione** della procedura guidata usare i valori predefiniti e scegliere **Avanti**.

11. Completare la procedura guidata. È possibile monitorare lo stato di avanzamento della distribuzione nel nodo **Distribuzioni** dell'area di lavoro **Monitoraggio**.

Il pacchetto verrà ora distribuito alla raccolta di destinazione e l'installazione invisibile all'utente di .NET Framework 4.5 avrà inizio. Per informazioni sui codici di errore di installazione di .NET Framework 4.5, vedere la sezione [Codici restituiti](#return_codes) più avanti in questo argomento.

<a name="resources"></a>

## <a name="resources"></a>Risorse

Per altre informazioni riguardanti l'infrastruttura per testare la distribuzione del pacchetto ridistribuibile di .NET Framework 4.5, vedere le risorse seguenti.

**Active Directory, DNS, DHCP:**

- [Active Directory Domain Services](/windows/desktop/ad/active-directory-domain-services)

- [Domain Name System (DNS)](/windows-server/networking/dns/dns-top)

- [Dynamic Host Configuration Protocol (DHCP)](/windows-server/networking/technologies/dhcp/dhcp-top)

**SQL Server 2008:**

- [Installazione di SQL Server 2008 (video di SQL Server)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))

- [SQL Server 2008 Security Overview for Database Administrators (Panoramica della sicurezza di SQL Server 2008 per gli amministratori di database)](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

**System Center 2012 Configuration Manager (punto di gestione, punto di distribuzione):**

- [Amministrazione del sito per System Center 2012 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg681983%28v=technet.10%29)

- [Configuration Manager Single Site Planning and Deployment (Pianificazione e distribuzione in modalità sito singolo di Configuration Manager)](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb680961%28v=technet.10%29)

**Client di System Center 2012 Configuration Manager per computer Windows:**

- [Distribuzione dei client per System Center 2012 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699391%28v=technet.10%29)

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="log-file-locations"></a>Percorsi dei file di log

Durante l'installazione di .NET Framework vengono generati i seguenti file di log:

- %temp%\Microsoft .NET Framework *Version* \* . txt
- %temp%\Microsoft .NET Framework *Version* \* . html

dove *versione* è la versione di .NET Framework che si sta installando, ad esempio 4.5 o 4.7.2.

È anche possibile specificare la directory in cui vengono scritti i file di log usando l'opzione della riga di comando `/log` nel comando di installazione di .NET Framework. Per altre informazioni, vedere la [Guida alla distribuzione di .NET Framework per sviluppatori](deployment-guide-for-developers.md#command-line-options).

È possibile usare lo [strumento di raccolta dei log](https://www.microsoft.com/download/details.aspx?id=12493) per raccogliere i file di log di .NET Framework e creare un file CAB compresso che riduce le dimensioni dei file.

<a name="return_codes"></a>

### <a name="return-codes"></a>Codici restituiti

Nella tabella seguente vengono elencati i codici più comuni restituiti dal programma di installazione ridistribuibile .NET Framework 4.5. I codici restituiti sono gli stessi per tutte le versioni del programma di installazione.

Per collegamenti a informazioni dettagliate, vedere la sezione successiva, [Scaricare i codici di errore](#additional_error_codes).

|Codice restituito|Descrizione|
|-----------------|-----------------|
|0|Installazione completata.|
|1602|Installazione annullata dall'utente.|
|1603|Errore irreversibile durante l'installazione.|
|1641|Riavvio necessario per completare l'installazione. Questo messaggio indica l'esito positivo dell'operazione.|
|3010|Riavvio necessario per completare l'installazione. Questo messaggio indica l'esito positivo dell'operazione.|
|5100|Il computer dell'utente non soddisfa i requisiti di sistema.|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a>Scaricare i codici di errore

- [Background Intelligent Transfer Service (BITS) error codes](/windows/desktop/Bits/bits-return-values) (Codici di errore del Servizio trasferimento intelligente in background (BITS))

- [Codici di errore del moniker URL](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145%28v=vs.85%29)

- [WinHttp error codes](/windows/desktop/WinHttp/error-messages) (Codici di errore WinHttp)

Altri codici di errore:

- [Windows Installer error codes](/windows/desktop/msi/error-codes) (Codici di errore di Windows Installer)

- [Windows Update Agent result codes](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10)) (Codici restituiti dall'Agente di Windows Update)

## <a name="see-also"></a>Vedere anche

- [Guida alla distribuzione per gli sviluppatori](deployment-guide-for-developers.md)
- [System Requirements](../get-started/system-requirements.md)
