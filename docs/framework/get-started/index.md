---
title: Introduzione a .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- .NET Framework, getting started
- getting started [.NET Framework]
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
ms.openlocfilehash: d210d31f38af5c6cc21bf9b743ac4e1320db081f
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837038"
---
# <a name="get-started-with-the-net-framework"></a>Introduzione a .NET Framework

.NET Framework è un ambiente di esecuzione runtime in cui vengono gestite le app destinate a .NET Framework. È costituito da Common Language Runtime, che fornisce la gestione della memoria e altri servizi di sistema, e da un'ampia libreria di classi, che consente ai programmatori di sfruttare codice affidabile per tutte le aree principali dello sviluppo di app.

> [!NOTE] 
> .NET Framework è disponibile solo nei sistemi Windows. È possibile usare [.NET Core](../../core/index.md) per eseguire app in Windows, MacOS e Linux. 

## <a name="Introducing"></a> Cos'è .NET Framework?

.NET Framework è un ambiente di esecuzione gestita per Windows che fornisce un'ampia gamma di servizi alle app in esecuzione. È costituito da due componenti principali: Common Language Runtime (CLR), vale a dire il motore di esecuzione mediante il quale vengono gestite le app in esecuzione, e la libreria di classi .NET Framework, che fornisce una raccolta di codice testato e riutilizzabile che gli sviluppatori possono chiamare dalle rispettive app. Tra i servizi forniti da .NET Framework per le app in esecuzione sono inclusi:

- Gestione della memoria. In molti linguaggi di programmazione, i programmatori sono responsabili dell'allocazione e del rilascio di memoria, nonché della gestione della durata degli oggetti. Nelle app .NET Framework, CLR fornisce questi servizi per conto dell'app.

- Common Type System. Nei linguaggi di programmazione tradizionali, i tipi di base vengono definiti dal compilatore, mediante il quale l'interoperabilità tra i linguaggi viene resa più complicata. In .NET Framework i tipi di base vengono definiti dal sistema di tipi di .NET Framework e sono comuni a tutti i linguaggi destinati a .NET Framework.

- Libreria di classi estesa. Anziché dover scrivere grandi quantità di codice per gestire operazioni comuni di programmazione di basso livello, i programmatori usano una libreria di tipi facilmente accessibile e i relativi membri dalla libreria di classi .NET Framework.

- Framework e tecnologie di sviluppo. In .NET Framework sono incluse librerie per aree specifiche dello sviluppo di app, ad esempio ASP.NET per app Web, ADO.NET per l'accesso ai dati, Windows Communication Foundation per app orientate ai servizi e Windows Presentation Foundation per le app desktop Windows.

- Interoperabilità del linguaggio. Tramite i compilatori di linguaggio destinati a .NET Framework viene generato un codice intermedio denominato Common Intermediate Language (CIL) che, a sua volta, viene compilato in fase di esecuzione tramite Common Language Runtime. Con questa funzionalità, le routine scritte in un linguaggio sono accessibili ad altri linguaggi e i programmatori si concentrano sulla creazione di app nei linguaggi preferiti.

- Compatibilità tra versioni. In rare eccezioni, le app sviluppate usando una particolare versione di .NET Framework vengono eseguite senza modifiche in una versione successiva.

- Esecuzione affiancata. .NET Framework consente di risolvere conflitti tra versioni permettendo la coesistenza di più versioni di Common Language Runtime nello stesso computer. Ciò significa che possono coesistere più versioni di app e che un'app può essere eseguita nella versione di .NET Framework con cui è stata creata. L'esecuzione side-by-side è possibile per i gruppi di versioni di .NET Framework 1.0/1.1, 2.0/3.0/3.5 e 4/4.5.x/4.6.x/4.7.x/4.8.

- Multitargeting. Usando [.NET Standard](../../standard/net-standard.md) come destinazione, gli sviluppatori possono creare librerie di classi che funzionano su più piattaforme .NET Framework supportate da tale versione dello standard. Ad esempio, le librerie basate su .NET Standard 2.0 possono essere usate dalle app sviluppate per .NET Framework 4.6.1, .NET Core 2.0 e UWP 10.0.16299. 

<a name="ForUsers"></a>
## <a name="the-net-framework-for-users"></a>.NET Framework per utenti

Se non si sviluppano ma si usano app .NET Framework, non è necessario avere una specifica conoscenza di .NET Framework o del relativo funzionamento. .NET Framework è sostanzialmente trasparente agli utenti.

Se si usa il sistema operativo Windows, .NET Framework potrebbe essere già installato nel computer. Inoltre, se si installa un'app per cui è richiesto .NET Framework, è possibile che tramite il programma di installazione dell'app venga installata una versione specifica di .NET Framework nel computer in uso. In alcuni casi, potrebbe essere visualizzata una finestra di dialogo in cui viene chiesto di installare .NET Framework. Se si è appena provato a eseguire un'app quando viene visualizzata questa finestra di dialogo e se il computer ha accesso a Internet, è possibile aprire una pagina Web che consente di installare la versione mancante di .NET Framework. Per altre informazioni, vedere la [Guida all'installazione](../install/index.md).

In generale, le versioni di .NET Framework installate nel computer non devono essere disinstallate per due motivi:

- Se un'app in uso dipende da una specifica versione di .NET Framework che viene rimossa, l'app potrebbe smettere di funzionare.

- Alcune versioni di .NET Framework sono aggiornamenti sul posto di versioni precedenti. Ad esempio, .NET Framework 3.5 è un aggiornamento sul posto alla versione 2.0 e .NET Framework 4.8 è un aggiornamento sul posto alle versioni da 4 a 4.7.2. Per altre informazioni, vedere [Versioni e dipendenze di .NET Framework](../migration-guide/versions-and-dependencies.md).

Nelle versioni di Windows precedenti a Windows 8, se si sceglie di rimuovere .NET Framework, per la disinstallazione usare sempre **Programmi e funzionalità** dal Pannello di controllo. Non rimuovere mai manualmente una versione di .NET Framework. In Windows 8 e versioni successive, .NET Framework è un componente del sistema operativo e non può essere disinstallato in modo indipendente.

Si noti che più versioni di .NET Framework possono coesistere contemporaneamente in un computer. Ciò significa che non è necessario disinstallare le versioni precedenti per installare una versione più recente.

## <a name="ForDevelopers"></a> .NET Framework per sviluppatori

Uno sviluppatore può scegliere qualsiasi linguaggio di programmazione che supporta .NET Framework per creare le app. Poiché .NET Framework fornisce interoperabilità e indipendenza dal linguaggio, è possibile interagire con altri componenti e app .NET Framework indipendentemente dal linguaggio con cui sono stati sviluppati.

Per sviluppare app o componenti .NET Framework, eseguire le operazioni seguenti:

1. Se non è già preinstallata nel sistema operativo, installare la versione di .NET Framework che verrà usata dall'app. La versione di produzione più recente è .NET Framework 4.8, preinstallata nell'aggiornamento di maggio 2019 di Windows 10 e disponibile per il download nelle versioni precedenti del sistema operativo Windows. Per i requisiti di sistema di .NET Framework, vedere [Requisiti di sistema](system-requirements.md). Per informazioni sull'installazione di .NET Framework, vedere [Guida all'installazione](../install/guide-for-developers.md). Pacchetti aggiuntivi di .NET Framework vengono rilasciati fuori programma, ovvero all'occorrenza al di fuori di qualsiasi ciclo di rilascio regolare o pianificato. Per informazioni su questi pacchetti, vedere [.NET Framework e rilascio fuori programma](the-net-framework-and-out-of-band-releases.md).

2. Selezionare uno o più linguaggi supportati da .NET Framework che si intende usare per lo sviluppo delle app. Sono disponibili numerosi linguaggi, tra cui [Visual Basic](../../visual-basic/index.yml), [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) e [C++/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) di Microsoft. Un linguaggio di programmazione che consente di sviluppare app per .NET Framework è conforme alla [specifica CLI (Common Language Infrastructure)](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/).

3. Selezionare e installare l'ambiente di sviluppo da usare per creare le app e che supporti uno o più linguaggi di programmazione selezionati. L'ambiente di sviluppo integrato (IDE) Microsoft per le app .NET Framework è [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). È disponibile in numerose edizioni.

Per altre informazioni sullo sviluppo di app destinate a .NET Framework, vedere la [Guida di sviluppo](../development-guide.md).

## <a name="related-articles"></a>Articoli correlati

| Titolo | Descrizione |
| ----- |------------ |
| [Panoramica](overview.md) | Vengono fornite informazioni dettagliate per gli sviluppatori che realizzano app destinate a .NET Framework. |
| [Guida all'installazione](../install/index.md) | Vengono fornite informazioni sull'installazione di .NET Framework. |  
| [.NET Framework e rilascio fuori programma](the-net-framework-and-out-of-band-releases.md) | Vengono descritti i rilasci fuori programma di .NET Framework e viene illustrato come usarli nell'app. |
| [Requisiti di sistema](system-requirements.md) | Vengono elencati i requisiti hardware e software per l'esecuzione di .NET Framework. |
| [Componenti di base e open-source di .NET](net-core-and-open-source.md) | Viene descritto .NET Core in relazione a .NET Framework e viene spiegato come accedere ai progetti .NET Core open source. |
| [Documentazione di .NET Core](../../core/index.md) | Documentazione concettuale e di riferimento delle API per .NET Core. |
| [.NET Standard](../../standard/net-standard.md) | Viene descritto .NET Standard, una specifica con versione supportata dalle singole implementazioni di .NET per garantire la disponibilità di un set coerente di API in più piattaforme.

## <a name="see-also"></a>Vedere anche

- [Guida a .NET Framework](../index.md)
- [Novità](../whats-new/index.md)
- [Browser API .NET](../../../api/index.md)
- [Guida di sviluppo](../development-guide.md)
