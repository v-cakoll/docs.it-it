---
title: Risorse nelle app .NET
description: Informazioni sulle risorse nelle app .NET. Una risorsa è rappresentata da tutti i dati non eseguibili distribuiti logicamente con un'app.
ms.date: 07/25/2018
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- deploying applications [.NET Core], resources
- application resources
- resource files
- satellite assemblies
- localization
- packaging application resources
- localizing resources
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
ms.openlocfilehash: 105325170389917bfb2022314791aa1ed5923db3
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865164"
---
# <a name="resources-in-net-apps"></a>Risorse nelle app .NET

L'utilizzo di risorse è richiesto in quasi tutte le applicazioni destinate a un impiego professionale. Una risorsa è costituita da dati non eseguibili che vengono distribuiti in modo logico con un'applicazione. Una risorsa può essere visualizzata in un'applicazione sotto forma di messaggi di errore o come parte dell'interfaccia utente. Le risorse possono contenere dati in diversi formati, tra cui stringhe, immagini e oggetti persistenti. Per scrivere oggetti salvati in modo permanente in un file di risorse, gli oggetti devono essere serializzabili. L'archiviazione dei dati in un file di risorse consente di modificare i dati senza ricompilare l'intera app. Inoltre permette di archiviare i dati in un'unica posizione e non è più necessario basarsi sui dati specificati a livello di codice archiviati in più posizioni.

.NET Framework e .NET Core offrono ampio supporto per la creazione e la localizzazione di risorse. .NET supporta inoltre un modello semplice per la creazione del pacchetto di risorse localizzate e la relativa distribuzione.

Per informazioni sulle risorse in ASP.NET, vedere [Cenni preliminari sulle risorse delle pagine Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).

## <a name="create-and-localize-resources"></a>Creare e localizzare risorse

In un'applicazione non localizzata, è possibile utilizzare i file di risorse come repository per i dati dell'applicazione, in particolare per le stringhe che altrimenti possono essere hard-coded in più posizioni nel codice sorgente. In genere, le risorse vengono create come testo, con estensione txt o come o file XML (RESX) e si utilizza [Resgen.exe (Resource File Generator)](../tools/resgen-exe-resource-file-generator.md) per compilarle in file binari con estensione resources. Questi file possono quindi essere incorporati nel file eseguibile dell'applicazione tramite un compilatore di linguaggio. Per altre informazioni sulla creazione di file di risorse, vedere [Creazione di file di risorse](creating-resource-files-for-desktop-apps.md).

È anche possibile localizzare le risorse dell'applicazione per impostazioni cultura specifiche. In questo modo è possibile compilare versioni localizzate (tradotte) delle applicazioni. Quando si sviluppa un'applicazione in cui vengono utilizzate risorse localizzate, è possibile definire delle impostazioni cultura che fungono da impostazioni cultura non associate ad alcun paese o di fallback le cui risorse vengono utilizzate se non ve ne sono di appropriate. In genere, le risorse delle impostazioni cultura non associate ad alcun paese vengono archiviate nel file eseguibile dell'applicazione. Le risorse rimanenti per le singole impostazioni cultura localizzate vengono archiviate in assembly satellite autonomi. Per altre informazioni, vedere [Creazione di assembly satellite](creating-satellite-assemblies-for-desktop-apps.md).

## <a name="package-and-deploy-resources"></a>Creare il pacchetto e distribuire le risorse

Si sviluppano risorse di applicazioni localizzate in [assembly satellite](packaging-and-deploying-resources-in-desktop-apps.md). In un assembly satellite sono contenute le risorse di singole impostazioni cultura e non il codice dell'applicazione. Nel modello di distribuzione dell'assembly satellite si crea un'applicazione con un assembly predefinito (in genere l'assembly principale) e un assembly satellite per tutte le impostazioni cultura supportate dall'applicazione. Poiché gli assembly satellite non fanno parte dell'assembly principale, è possibile sostituire o aggiornare facilmente le risorse corrispondenti a impostazioni cultura specifiche senza sostituire l'assembly principale dell'applicazione.

Determinare con attenzione le risorse che costituiranno l'assembly di risorse predefinito dell'applicazione. Poiché tale assembly fa parte dell'assembly principale, le eventuali modifiche apportate richiederanno la sostituzione dell'assembly principale. Se non viene fornita una risorsa predefinita, quando il [processo di recupero di una risorsa](packaging-and-deploying-resources-in-desktop-apps.md) di riserva proverà a cercarla verrà generata un'eccezione. In un'applicazione progettata correttamente, l'utilizzo delle risorse non deve mai generare un'eccezione.

Per ulteriori informazioni, leggere l'articolo [Creazione del package e distribuzione delle risorse](packaging-and-deploying-resources-in-desktop-apps.md).

## <a name="retrieve-resources"></a>Recuperare le risorse

In fase di esecuzione, tramite un'applicazione vengono caricate le risorse localizzate appropriate per ciascun thread, in base alle impostazioni cultura specificate dalla proprietà <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>. Questo valore della proprietà viene derivato come segue:

- Assegnando direttamente un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura localizzate alla proprietà <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>.

- Se le impostazioni cultura non vengono assegnate in modo esplicito, recuperando le impostazioni cultura dell'interfaccia utente del thread predefinito dalla proprietà <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType>.

- Se le impostazioni cultura dell'interfaccia utente di un thread predefinito non vengono assegnate in modo esplicito, recuperando le impostazioni cultura per l'utente corrente del computer locale. Le implementazioni di .NET in esecuzione in Windows eseguono questa operazione chiamando la funzione di Windows [`GetUserDefaultUILanguage`](/windows/desktop/api/winnls/nf-winnls-getuserdefaultuilanguage) .

Per ulteriori informazioni su come vengono impostate le impostazioni cultura correnti dell'interfaccia utente, vedere le pagine di riferimento <xref:System.Globalization.CultureInfo> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>.

È quindi possibile recuperare le risorse per le impostazioni cultura correnti dell'interfaccia utente o per impostazioni cultura specifiche utilizzando la classe <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Sebbene la classe <xref:System.Resources.ResourceManager> sia maggiormente usata per il recupero delle risorse, nello spazio dei nomi <xref:System.Resources?displayProperty=nameWithType> sono contenuti tipi aggiuntivi utilizzabili per recuperare le risorse. Queste includono:

- La classe <xref:System.Resources.ResourceReader>, che consente di enumerare le risorse incorporate in un assembly o archiviate in un file binario autonomo con estensione resources. È utile quando non si conoscono i nomi esatti delle risorse disponibili in fase di esecuzione.

- La classe <xref:System.Resources.ResXResourceReader> che consente di recuperare le risorse da un file XML (con estensione resx).

- La classe <xref:System.Resources.ResourceSet> che consente di recuperare le risorse di impostazioni cultura specifiche senza rispettare le regole di fallback. Le risorse possono essere archiviate in un assembly o un file binario autonomo con estensione resources. È inoltre possibile sviluppare un'implementazione dell'oggetto <xref:System.Resources.IResourceReader> che consente di utilizzare la classe <xref:System.Resources.ResourceSet> per recuperare le risorse da un'altra origine.

- La classe <xref:System.Resources.ResXResourceSet> che consente di recuperare tutti gli elementi in un file di risorse XML in memoria.

## <a name="see-also"></a>Vedi anche

- <xref:System.Globalization.CultureInfo>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>
- [Creazione dei file di risorsa](creating-resource-files-for-desktop-apps.md)
- [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md)
- [Creazione di assembly satellite](creating-satellite-assemblies-for-desktop-apps.md)
- [Recupero di risorse](retrieving-resources-in-desktop-apps.md)
