---
title: Guida alla sicurezza di BinaryFormatter
description: In questo articolo vengono descritti i rischi di sicurezza inerenti al tipo BinaryFormatter e i consigli per i diversi serializzatori da utilizzare.
ms.date: 07/11/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: f6a54b34bbf1e19212fe37aadb448a1722fe9ff0
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444766"
---
# <a name="binaryformatter-security-guide"></a>Guida alla sicurezza di BinaryFormatter

Questo articolo si applica alle seguenti implementazioni di .NET:

* .NET Framework tutte le versioni
* .NET Core 2,1-3,1
* .NET 5,0 e versioni successive

## <a name="background"></a>Background

> [!WARNING]
> Il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> tipo è pericoloso ed è ***sconsigliato*** per l'elaborazione dei dati. Le applicazioni devono smettere di usare `BinaryFormatter` il prima possibile, anche se ritengono che i dati che stanno elaborando siano affidabili. `BinaryFormatter`non può essere protetto in modo sicuro.

Questo articolo si applica anche ai tipi seguenti:

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Web.UI.ObjectStateFormatter>

Le vulnerabilità di deserializzazione sono una categoria di minacce in cui i payload delle richieste vengono elaborati in modo non sicuro. Un utente malintenzionato che usa correttamente queste vulnerabilità in un'app può causare attacchi di tipo Denial of Service (DoS), divulgazione di informazioni o esecuzione di codice in modalità remota all'interno dell'app di destinazione. Questa categoria di rischio rende coerenti le [prime 10 OWASP](https://owasp.org/www-project-top-ten/). Le destinazioni includono app scritte in [un'ampia gamma di linguaggi](https://owasp.org/www-community/vulnerabilities/Deserialization_of_untrusted_data), tra cui C/C++, Java e C#.

In .NET, la destinazione di rischio maggiore è rappresentata dalle app che usano il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> tipo per deserializzare i dati. `BinaryFormatter`viene ampiamente usato nell'ecosistema .NET grazie alla potenza e alla semplicità d'uso. Tuttavia, questa stessa alimentazione offre agli utenti malintenzionati la possibilità di influenzare il flusso di controllo all'interno dell'app di destinazione. Gli attacchi riusciti possono comportare che l'utente malintenzionato sia in grado di eseguire il codice nel contesto del processo di destinazione.

Come analogia più semplice, si supponga che `BinaryFormatter.Deserialize` la chiamata su un payload equivale a interpretare il payload come eseguibile autonomo e come avviarlo.

## <a name="binaryformatter-security-vulnerabilities"></a>Vulnerabilità della sicurezza di BinaryFormatter

> [!WARNING]
> Il `BinaryFormatter.Deserialize` metodo __non è mai__ sicuro se usato con input non attendibile. È consigliabile che i consumer considerino invece una delle alternative descritte più avanti in questo articolo.

`BinaryFormatter`è stato implementato prima che le vulnerabilità di deserializzazione fossero una categoria di minacce ben riconosciuta. Di conseguenza, il codice non segue le procedure consigliate moderne. Il `Deserialize` metodo può essere usato come vettore per impedire agli utenti malintenzionati di eseguire attacchi DOS contro l'utilizzo di app. Questi attacchi potrebbero rendere l'applicazione non risponde o comportare una chiusura imprevista del processo. Non è possibile mitigare questa categoria di attacchi con una `SerializationBinder` o con altre `BinaryFormatter` Opzioni di configurazione. .NET considera questo comportamento come ***da progettazione*** e non emette un aggiornamento del codice per modificare il comportamento.

`BinaryFormatter.Deserialize`potrebbe essere vulnerabile ad altre categorie di attacchi, ad esempio la divulgazione di informazioni o l'esecuzione di codice in modalità remota. L'utilizzo di funzionalità come una personalizzata <xref:System.Runtime.Serialization.SerializationBinder> potrebbe non essere sufficiente per attenuare correttamente questi rischi. Esiste la possibilità che venga individuata una nuova vulnerabilità per cui .NET non è in grado di pubblicare un aggiornamento della sicurezza. I consumer devono valutare i singoli scenari e prendere in considerazione la loro potenziale esposizione a questi rischi.

È consigliabile che `BinaryFormatter` i consumer eseguano valutazioni dei rischi individuali sulle app. È responsabilità dell'utente determinare se usare `BinaryFormatter` . I consumer dovrebbero valutare i requisiti di sicurezza, tecnici, di reputazione, legali e normativi dell'uso di `BinaryFormatter` .

## <a name="preferred-alternatives"></a>Alternative preferite

.NET offre diversi serializzatori in-box che possono gestire i dati non attendibili in modo sicuro:

* <xref:System.Xml.Serialization.XmlSerializer>e <xref:System.Runtime.Serialization.DataContractSerializer> per serializzare gli oggetti grafici in e da XML. Non confondere `DataContractSerializer` con <xref:System.Runtime.Serialization.NetDataContractSerializer> .
* <xref:System.IO.BinaryReader>e <xref:System.IO.BinaryWriter> per XML e JSON.
* <xref:System.Text.Json>API per la serializzazione di oggetti grafici in JSON.

## <a name="dangerous-alternatives"></a>Alternative pericolose

Evitare i serializzatori seguenti:

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.ObjectStateFormatter>

I serializzatori precedenti eseguono tutte la deserializzazione polimorfica senza restrizioni e sono pericolose, proprio come `BinaryFormatter` .

## <a name="the-risks-of-assuming-data-to-be-trustworthy"></a>Rischi derivanti dal presupposto che i dati siano affidabili

Spesso, uno sviluppatore di app potrebbe ritenere che stiano elaborando solo un input attendibile. Il caso di input sicuro è true in alcune circostanze rare. Ma è molto più comune che un payload attraversi un confine di trust senza che lo sviluppatore lo realizzi.

Si __consideri un server locale in__ cui i dipendenti usano un client desktop dalle rispettive workstation per interagire con il servizio. Questo scenario può essere considerato ingenuamente come un programma di installazione "sicuro" in cui l'utilizzo `BinaryFormatter` è accettabile. Tuttavia, questo scenario presenta un vettore per il malware che ottiene l'accesso al computer di un singolo dipendente per potersi diffondere nell'intera azienda. Il malware può sfruttare l'uso dell'azienda di `BinaryFormatter` per spostarsi lateralmente dalla workstation del dipendente al server back-end. Può quindi sottrarre i dati sensibili della società. Tali dati possono includere segreti commerciali o dati dei clienti.

__Si consideri anche un'app che usa `BinaryFormatter` per salvare in modo permanente lo stato.__ Questo potrebbe sembrare inizialmente uno scenario sicuro, perché la lettura e la scrittura dei dati sul disco rigido rappresentano una minaccia secondaria. Tuttavia, la condivisione di documenti attraverso la posta elettronica o Internet è comune e la maggior parte degli utenti finali non può percepire l'apertura di questi file scaricati come comportamento rischioso.

Questo scenario può essere sfruttato per effetto nefasto. Se l'app è un gioco, gli utenti che condividono i file di salvataggio inconsapevolmente si trovano a rischio. Gli sviluppatori possono anche essere assegnati. L'autore dell'attacco potrebbe inviare un messaggio di posta elettronica al supporto tecnico degli sviluppatori, collegando un file di dati dannosi e chiedendo al personale del supporto di aprirlo. Questo tipo di attacco potrebbe dare all'utente malintenzionato un punto di appoggio nell'azienda.

Un altro scenario è la posizione in cui il file di dati viene archiviato nella memoria cloud e sincronizzato automaticamente tra i computer dell'utente. Un utente malintenzionato che è in grado di ottenere l'accesso all'account di archiviazione cloud può avvelenare il file di dati. Questo file di dati verrà sincronizzato automaticamente con i computer dell'utente. Alla successiva apertura del file di dati da parte dell'utente, viene eseguito il payload del pirata informatico. Pertanto, l'autore dell'attacco può sfruttare la compromissione di un account di archiviazione cloud per ottenere le autorizzazioni di esecuzione del codice completo.

__Si consideri un'app che passa da un modello di installazione desktop a un modello cloud-First.__ Questo scenario include le app che passano da un'app desktop o un modello rich client in un modello basato sul Web. Tutti i modelli di rischio creati per l'app desktop non sono necessariamente applicabili al servizio basato sul cloud. Il modello di minaccia per l'app desktop potrebbe ignorare una determinata minaccia come "non interessante per il client di attaccare se stesso". Tuttavia, la stessa minaccia potrebbe diventare interessante quando considera un utente remoto (il client) che attacca il servizio cloud.

> [!NOTE]
> In termini generali, lo scopo della serializzazione è trasmettere un oggetto all'interno o all'esterno di un'app. Un esercizio di modellazione delle minacce contrassegna quasi sempre questo tipo di trasferimento dei dati come superamento di un confine di trust.

## <a name="further-resources"></a>Altre risorse

* [YSoSerial.NET](https://github.com/pwntester/ysoserial.net) per la ricerca di come gli avversari attaccano le app che usano `BinaryFormatter` .
* [Modellazione delle minacce](/securityengineering/sdl/threatmodeling) per informazioni sulle app e i servizi di modellazione delle minacce.
* Background generale sulle vulnerabilità di deserializzazione:
  * [OWASP Top 10-A8:2017-deserializzazione non sicura](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A8-Insecure_Deserialization)
  * [CWE-502: deserializzazione di dati non attendibili](https://cwe.mitre.org/data/definitions/502.html)
