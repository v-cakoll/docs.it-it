---
title: Introduzione a .NET Framework
description: Introduzione a .NET, un ambiente di esecuzione di runtime che gestisce le app. Contiene un Common Language Runtime (CLR) e una libreria di classi estesa.
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- .NET Framework, getting started
- getting started [.NET Framework]
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
ms.openlocfilehash: b6ad74d2984443a3b8345c2261996e7ab30acdff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621652"
---
# <a name="get-started-with-net-framework"></a>Inizia a usare .NET Framework

.NET Framework è un ambiente di esecuzione in fase di esecuzione che gestisce le app destinate .NET Framework. È costituito da Common Language Runtime, che fornisce la gestione della memoria e altri servizi di sistema, e da un'ampia libreria di classi, che consente ai programmatori di sfruttare codice affidabile per tutte le aree principali dello sviluppo di app.

> [!NOTE]
> .NET Framework è disponibile solo nei sistemi Windows. È possibile usare [.NET Core](../../core/index.yml) per sviluppare ed eseguire app in Windows, MacOS e Linux.

## <a name="what-is-net-framework"></a>Che cos'è .NET Framework?

.NET Framework è un ambiente di esecuzione gestito per Windows che offre un'ampia gamma di servizi alle applicazioni in esecuzione. È costituito da due componenti principali: Common Language Runtime (CLR), vale a dire il motore di esecuzione mediante il quale vengono gestite le app in esecuzione, e la libreria di classi .NET Framework, che fornisce una raccolta di codice testato e riutilizzabile che gli sviluppatori possono chiamare dalle rispettive app. I servizi forniti da .NET Framework per le app in esecuzione includono quanto segue:

- Gestione della memoria. In molti linguaggi di programmazione, i programmatori sono responsabili dell'allocazione e del rilascio di memoria, nonché della gestione della durata degli oggetti. Nelle app .NET Framework, CLR fornisce questi servizi per conto dell'app.

- Common Type System. Nei linguaggi di programmazione tradizionali, i tipi di base vengono definiti dal compilatore, mediante il quale l'interoperabilità tra i linguaggi viene resa più complicata. In .NET Framework i tipi di base vengono definiti dal sistema di tipi di .NET Framework e sono comuni a tutti i linguaggi destinati .NET Framework.

- Libreria di classi estesa. Anziché dover scrivere grandi quantità di codice per gestire operazioni comuni di programmazione di basso livello, i programmatori usano una libreria di tipi facilmente accessibile e i relativi membri dalla libreria di classi .NET Framework.

- Framework e tecnologie di sviluppo. .NET Framework include librerie per aree specifiche dello sviluppo di app, ad esempio ASP.NET per app Web, ADO.NET per l'accesso ai dati, Windows Communication Foundation per le app orientate ai servizi e Windows Presentation Foundation per le app desktop di Windows.

- Interoperabilità del linguaggio. I compilatori di linguaggio destinati a .NET Framework emettono un codice intermedio denominato Common Intermediate Language (CIL), che, a sua volta, viene compilato in fase di esecuzione dal Common Language Runtime. Con questa funzionalità, le routine scritte in un linguaggio sono accessibili ad altri linguaggi e i programmatori si concentrano sulla creazione di app nei linguaggi preferiti.

- Compatibilità tra versioni. Con eccezioni rare, le app sviluppate usando una particolare versione di .NET Framework vengono eseguite senza modifiche in una versione successiva.

- Esecuzione affiancata. .NET Framework consente di risolvere i conflitti di versione consentendo la presenza di più versioni del Common Language Runtime nello stesso computer. Ciò significa che più versioni di app possono coesistere e che un'app può essere eseguita nella versione di .NET Framework con cui è stata compilata. L'esecuzione side-by-side è possibile per i gruppi di versioni di .NET Framework 1.0/1.1, 2.0/3.0/3.5 e 4/4.5.x/4.6.x/4.7.x/4.8.

- Multitargeting. Usando [.NET Standard](../../standard/net-standard.md) come destinazione, gli sviluppatori possono creare librerie di classi che funzionano su più piattaforme .NET Framework supportate da tale versione dello standard. Ad esempio, le librerie destinate a .NET Standard 2,0 possono essere usate da app destinate .NET Framework 4.6.1, .NET Core 2,0 e UWP) 10.0.16299.

<a name="ForUsers"></a>
## <a name="the-net-framework-for-users"></a>.NET Framework per utenti

Se non si sviluppano app .NET Framework, ma le si usa, non è necessario avere conoscenze specifiche su .NET Framework o sul suo funzionamento. Nella maggior parte dei casi, il Framework è completamente trasparente agli utenti.

Se si usa il sistema operativo Windows, .NET Framework possibile che sia già installato nel computer. Inoltre, se si installa un'app che richiede .NET Framework, il programma di installazione dell'applicazione potrebbe installare una versione specifica del Framework nel computer. In alcuni casi, è possibile che venga visualizzata una finestra di dialogo in cui viene chiesto di installare .NET Framework. Se si è appena provato a eseguire un'app quando viene visualizzata questa finestra di dialogo e se il computer ha accesso a Internet, è possibile passare a una pagina Web che consente di installare la versione mancante di .NET Framework. Per ulteriori informazioni, vedere la [Guida all'installazione](../install/index.md).

In generale, non è necessario disinstallare le versioni di .NET Framework installate nel computer. per due motivi:

- Se un'app usata dipende da una versione specifica di .NET Framework, l'app potrebbe interrompersi se la versione viene rimossa.

- Alcune versioni di .NET Framework sono aggiornamenti sul posto delle versioni precedenti. Ad esempio, .NET Framework 3,5 è un aggiornamento sul posto alla versione 2,0 e .NET Framework 4,8 è un aggiornamento sul posto alle versioni da 4 a 4.7.2. Per altre informazioni, vedere [Versioni e dipendenze di .NET Framework](../migration-guide/versions-and-dependencies.md).

Nelle versioni di Windows precedenti a Windows 8, se si sceglie di rimuovere .NET Framework, utilizzare sempre **programmi e funzionalità** dal pannello di controllo per disinstallarlo. Non rimuovere mai manualmente una versione di .NET Framework. In Windows 8 e versioni successive .NET Framework è un componente del sistema operativo e non può essere disinstallato in modo indipendente.

Più versioni di .NET Framework possono coesistere contemporaneamente in un singolo computer. Ciò significa che non è necessario disinstallare le versioni precedenti per installare una versione più recente.

## <a name="net-framework-for-developers"></a>.NET Framework per gli sviluppatori

Gli sviluppatori scelgono qualsiasi linguaggio di programmazione che supporti .NET Framework per creare le app. Poiché .NET Framework fornisce l'indipendenza e l'interoperabilità del linguaggio, si interagisce con altre app e componenti .NET Framework indipendentemente dal linguaggio con cui sono stati sviluppati.

Per sviluppare app o componenti .NET Framework, eseguire le operazioni seguenti:

1. Se non è preinstallato nel sistema operativo, installare la versione di .NET Framework a cui verrà destinata l'app. La versione di produzione più recente è .NET Framework 4,8. È preinstallato in Windows 10 l'aggiornamento di 2019 maggio ed è disponibile per il download nelle versioni precedenti del sistema operativo Windows. Per i requisiti di sistema di .NET Framework, vedere [Requisiti di sistema](system-requirements.md). Per informazioni sull'installazione di altre versioni di .NET Framework, vedere la [Guida all'installazione](../install/guide-for-developers.md). Pacchetti aggiuntivi di .NET Framework vengono rilasciati fuori programma, ovvero all'occorrenza al di fuori di qualsiasi ciclo di rilascio regolare o pianificato. Per informazioni su questi pacchetti, vedere [.NET Framework e versioni fuori banda](the-net-framework-and-out-of-band-releases.md).

2. Selezionare la lingua o le lingue supportate dalla versione .NET Framework che si intende usare per sviluppare le app. Sono disponibili diversi linguaggi, tra cui [Visual Basic](../../visual-basic/index.yml), [C#](../../csharp/index.yml), [F #](../../fsharp/index.yml)e [C++/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) di Microsoft. Un linguaggio di programmazione che consente di sviluppare app per .NET Framework rispetta la [specifica Common Language Infrastructure (CLI)](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/).

3. Selezionare e installare l'ambiente di sviluppo da usare per creare le app e che supporti uno o più linguaggi di programmazione selezionati. L'ambiente di sviluppo integrato (IDE) Microsoft per le app .NET Framework è [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). È disponibile in numerose edizioni.

Per ulteriori informazioni sullo sviluppo di app destinate a .NET Framework, vedere la [Guida di sviluppo](../development-guide.md).

## <a name="related-articles"></a>Articoli correlati

| Titolo | Descrizione |
| ----- |------------ |
| [Panoramica](overview.md) | Fornisce informazioni dettagliate per gli sviluppatori che creano app destinate a .NET Framework. |
| [Guida all'installazione](../install/index.md) | Vengono fornite informazioni sull'installazione di .NET Framework. |  
| [.NET Framework e versioni fuori banda](the-net-framework-and-out-of-band-releases.md) | Vengono descritti i rilasci fuori programma di .NET Framework e viene illustrato come usarli nell'applicazione. |
| [Requisiti di sistema](system-requirements.md) | Elenca i requisiti hardware e software per l'esecuzione di .NET Framework. |
| [Componenti di base e open-source di .NET](net-core-and-open-source.md) | Viene descritto .NET Core in relazione a .NET Framework e come accedere ai progetti .NET Core open source. |
| [Documentazione di .NET Core](../../core/index.yml) | Documentazione concettuale e di riferimento delle API per .NET Core. |
| [.NET Standard](../../standard/net-standard.md) | Viene illustrato .NET Standard, una specifica con versione supportata dalle singole implementazioni .NET per garantire che un set coerente di API sia disponibile su più piattaforme.

## <a name="see-also"></a>Vedere anche

- [Guida a .NET Framework](../index.yml)
- [Novità](../whats-new/index.md)
- [Browser delle API .NET](../../../api/index.md)
- [Guida allo sviluppo](../development-guide.md)
