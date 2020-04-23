---
title: Marshalling di interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
ms.openlocfilehash: 70514811a9d236dc485f64fc34297cdb057a1512
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124279"
---
# <a name="interop-marshaling"></a>Marshalling di interoperabilità

Il marshalling di interoperabilità determina il passaggio di dati in argomenti di metodo e i valori restituiti tra memoria gestita e non gestita durante le chiamate. Il marshalling di interoperabilità è un'attività di run-time eseguita dal servizio di marshalling di Common Language Runtime.

La maggior parte dei tipi di dati hanno rappresentazioni comuni nella memoria gestita e non gestita. Il gestore di marshalling di interoperabilità gestisce questi tipi per conto dell'utente. Altri tipi possono essere ambigui o non essere rappresentati nella memoria gestita.

Un tipo ambiguo può avere più rappresentazioni non gestite che eseguono il mapping a un singolo tipo gestito o informazioni sul tipo mancante, ad esempio le dimensioni della matrice. Per i tipi ambigui, il gestore del marshalling fornisce una rappresentazione predefinita e rappresentazioni alternative in cui sono presenti più rappresentazioni. È possibile fornire istruzioni esplicite al gestore del marshalling su come eseguire il marshalling di un tipo ambiguo.

## <a name="platform-invoke-and-com-interop-models"></a>Modelli basati su platform invoke e sull'interoperabilità COM

In Common Language Runtime vengono forniti due meccanismi per l'interoperabilità con il codice non gestito:

- Platform invoke, che consente la chiamata di funzioni esportate da una libreria non gestita da parte del codice gestito.
- L'interoperabilità COM, che consente l'interazione del codice gestito con oggetti COM (Component Object Model) mediante interfacce.

Il marshalling di interoperabilità viene usato sia da platform invoke che dall'interoperabilità COM per spostare con precisione gli argomenti dei metodi tra chiamante e chiamato e viceversa, se necessario. Come mostrato nella figura seguente, una chiamata al metodo di platform invoke viene effettuata dal codice gestito al codice non gestito e mai viceversa, ad eccezione del caso in cui sono coinvolte [funzioni di callback](callback-functions.md). Benché il flusso delle chiamate platform invoke possa andare solo dal codice gestito a quello non gestito, il flusso dei dati può essere in entrambe le direzioni, come parametri di input o di output. Le chiamate al metodo di interoperabilità COM possono scorrere in entrambe le direzioni.

![Platform Invoke](./media/interop-marshaling/interop-marshaling-invoke-and-com.png "Flusso delle chiamate con i metodi di platform invoke e di interoperabilità COM")

Al livello inferiore, lo stesso servizio di marshalling di interoperabilità viene usato da entrambi i meccanismi. Alcuni tipi di dati sono tuttavia supportati esclusivamente dall'interoperabilità COM o da platform invoke. Per informazioni dettagliate, vedere [Comportamento di marshalling predefinito](default-marshaling-behavior.md).

## <a name="marshaling-and-com-apartments"></a>Marshalling e apartment COM

Il gestore di marshalling di interoperabilità esegue il marshalling dei dati tra l'heap di Common Language Runtime e quello non gestito. Il marshalling ha luogo ogni volta che il chiamante e il chiamato non possono operare sulla stessa istanza di dati. Il gestore di marshalling di interoperabilità fa sì che il chiamante e il chiamato sembrino operare sugli stessi dati benché dispongano ognuno della propria copia dei dati.

In COM è anche disponibile un gestore che effettua il marshalling dei dati tra apartment COM o diversi processi COM. Quando le chiamate tra codice gestito e non gestito sono effettuate all'interno dello stesso apartment COM, il gestore di marshalling di interoperabilità è il solo a essere coinvolto. Quando si effettuano chiamate tra codice gestito e non gestito in un diverso apartment COM o processo, sono coinvolti sia il gestore di marshalling COM che quello di interoperabilità.

### <a name="com-clients-and-managed-servers"></a>Server gestiti e client COM

Un server gestito esportato con una libreria dei tipi registrata da [Regasm.exe (strumento di registrazione di assembly)](../tools/regasm-exe-assembly-registration-tool.md) include una voce `ThreadingModel` del Registro di sistema impostata su `Both`. Questo valore indica che il server può essere attivato in un apartment a thread singolo (Single-Threaded Apartment, STA) o in un apartment con multithreading (Multithreaded Apartment, MTA). L'oggetto server viene creato nello stesso apartment del chiamante, come illustrato nella tabella seguente:

|Client COM|Server .NET|Requisiti di marshalling|
|----------------|-----------------|-----------------------------|
|STA|`Both` diventa STA.|Marshalling nello stesso apartment.|
|MTA|`Both` diventa MTA.|Marshalling nello stesso apartment.|

Poiché il client e il server si trovano nello stesso apartment, tutto il marshalling dei dati viene gestito automaticamente dal servizio di marshalling di interoperabilità. L'illustrazione seguente mostra il servizio di marshalling di interoperabilità tra gli heap gestiti e non gestiti all'interno dello stesso apartment di tipo COM.

![Marshalling di interoperabilità tra heap gestiti e non gestiti](./media/interop-marshaling/interop-heaps-managed-and-unmanaged.gif "Processo di marshalling nello stesso apartment")

Se si intende esportare un server gestito, ricordare che il client COM determina l'apartment del server. Un server gestito chiamato da un client COM inizializzato in un MTA deve garantire la thread safety.

### <a name="managed-clients-and-com-servers"></a>Client gestiti e server COM

Benché l'impostazione predefinita per gli apartment dei client gestiti sia MTA, è possibile che essa venga modificata dal tipo di applicazione del client .NET. L'impostazione di apartment per i client di Visual Basic, ad esempio, è STA. Per esaminare e modificare l'impostazione di apartment di un client gestito, è possibile usare l'oggetto <xref:System.STAThreadAttribute?displayProperty=nameWithType>, l'oggetto <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, la proprietà <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> o la proprietà <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType>.

L'autore del componente imposta l'affinità di thread di un server COM. La tabella riportata di seguito mostra le combinazioni delle impostazioni di apartment per i client .NET e i server COM, nonché i requisiti di marshalling per le diverse combinazioni.

|Client .NET|Server COM|Requisiti di marshalling|
|-----------------|----------------|-----------------------------|
|MTA (predefinito)|MTA<br /><br /> STA|Marshalling di interoperabilità.<br /><br /> Marshalling di interoperabilità e COM.|
|STA|MTA<br /><br /> STA|Marshalling di interoperabilità e COM.<br /><br /> Marshalling di interoperabilità.|

Quando un client gestito e un server non gestito si trovano nello stesso apartment, tutto il marshalling dei dati viene eseguito dal servizio di marshalling di interoperabilità. Tuttavia, quando il client e il server vengono inizializzati in apartment diversi, è necessario anche il marshalling COM. La figura seguente Mostra gli elementi di una chiamata tra più Apartment:

![Marshalling COM](./media/interop-marshaling/single-process-across-multi-apartment.gif "Chiamata su diversi apartment tra un client .NET e un oggetto COM")

Per effettuare il marshalling su diversi apartment, procedere come indicato di seguito:

- Accettare l'overhead del marshalling su diversi apartment, evidente solo quando sono presenti molte chiamate oltre il limite. Registrare la libreria dei tipi del componente COM per consentire alle chiamate di attraversare correttamente il limite dell'apartment.
- Modificare il thread principale impostando il thread del client su STA o MTA. Se il client C# chiama ad esempio molti componenti COM STA, è possibile evitare il marshalling su diversi apartment impostando il thread principale su STA.

    > [!NOTE]
    > Dopo avere impostato il thread di un client C# su STA, occorre effettuare il marshalling su diversi apartment per le chiamate ai componenti COM MTA.

Per istruzioni sulla selezione esplicita di un modello di apartment, vedere [Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100)).

## <a name="marshaling-remote-calls"></a>Marshalling di chiamate remote

Come per il marshalling su diversi apartment, si ricorre al marshalling COM nelle chiamate tra il codice gestito e non gestito ogni volta che gli oggetti si trovano in processi separati. Ad esempio:

- Un client COM che richiama un server gestito in un host remoto usa DCOM.
- Un client gestito che richiama un server COM su un host remoto usa DCOM.

Nella figura seguente viene illustrato il modo in cui il marshalling di interoperabilità e il marshalling COM forniscono canali di comunicazione tra i limiti del processo e

![Marshalling COM](./media/interop-marshaling/interop-and-com-marshaling.gif "Marshalling su diversi processi")

### <a name="preserving-identity"></a>Mantenimento dell'identità

In Common Language Runtime l'identità di riferimenti gestiti e non gestiti viene mantenuta. L'illustrazione riportata di seguito mostra il flusso di riferimenti non gestiti diretti (prima riga) e di riferimenti gestiti diretti (ultima riga) attraverso i limiti dell'host e del processo.

![COM callable wrapper e runtime callable wrapper](./media/interop-marshaling/interop-direct-ref-across-process.gif "Passaggio dei riferimenti attraverso i limiti dell'host e del processo")

In questa illustrazione:

- Un client non gestito recupera un riferimento a un oggetto COM da un oggetto gestito che lo recupera da un host remoto. Il meccanismo dei servizi remoti è DCOM.
- Un client gestito recupera un riferimento a un oggetto gestito da un oggetto COM che lo recupera da un host remoto. Il meccanismo dei servizi remoti è DCOM.

    > [!NOTE]
    > La libreria dei tipi esportata del server gestito deve essere registrata.

Il numero di limiti di processo tra chiamante e chiamato non è rilevante. La creazione di riferimenti diretti è identica per le chiamate in-process e per quelle out-of-process.

### <a name="managed-remoting"></a>Servizi remoti gestiti

Tra i servizi di runtime vengono inoltre forniti servizi remoti gestiti, utilizzabili per stabilire un canale di comunicazione tra gli oggetti gestiti attraverso i limiti dell'host e del processo. I servizi remoti gestiti possono contenere un firewall tra i componenti di comunicazione, come illustrato nella figura seguente:

![SOAP o TcpChannel](./media/interop-marshaling/interop-remote-soap-or-tcp.gif "Chiamate remote attraverso i firewall mediante SOAP o la classe TcpChannel") Chiamate remote tra firewall tramite SOAP o la classe TcpChannel

È possibile incanalare tramite SOAP alcune chiamate non gestite, ad esempio quelle tra i componenti serviti e COM.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Comportamento di marshalling predefinito](default-marshaling-behavior.md)|Descrive le regole usate dal servizio di marshalling di interoperabilità per effettuare il marshalling dei dati.|
|[Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md)|Descrive come dichiarare i parametri dei metodi e passare gli argomenti alle funzioni esportate dalle librerie non gestite.|
|[Dati di marshalling con interoperabilità COM](marshaling-data-with-com-interop.md)|Descrive come personalizzare i wrapper COM per modificare il comportamento di marshalling.|
|[Procedura: Eseguire la migrazione di codice gestito da DCOM a WCF](how-to-migrate-managed-code-dcom-to-wcf.md)|Descrive come eseguire la migrazione da DCOM a WCF.|
|[Procedura: Eseguire il mapping di HRESULT ed eccezioni](how-to-map-hresults-and-exceptions.md)|Descrive come mappare le eccezioni personalizzate agli oggetti HRESULT e illustra le relazioni di mapping tra ogni oggetto HRESULT e la classe di eccezioni corrispondente in .NET Framework.|
|[Interoperabilità tramite tipi generici](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))|Descrive le azioni supportate quando si usano tipi generici per l'interoperabilità COM.|
|[Interoperabilità con codice non gestito](index.md)|Descrive i servizi di interoperabilità forniti da Common Language Runtime.|
|[Interoperabilità COM avanzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))|Contiene collegamenti per accedere ad altre informazioni sull'inclusione di componenti COM nell'applicazione .NET Framework.|
|[Considerazioni di progettazione per l'interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))|Fornisce suggerimenti per la scrittura di componenti COM integrati.|

## <a name="reference"></a>Informazioni di riferimento

<xref:System.Runtime.InteropServices?displayProperty=nameWithType>
