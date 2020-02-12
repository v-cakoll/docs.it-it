---
title: Librerie di classi .NET
description: Informazioni sul modo in cui le librerie di classi di .NET consentono di raggruppare funzionalità utili in moduli che possono essere usati da più applicazioni.
author: richlander
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: a67484c3-fe92-44d8-8fa3-36fa2071d880
ms.openlocfilehash: b7934e5def202760ab05d363ee5fcda5d012ca72
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124585"
---
# <a name="net-class-libraries"></a>Librerie di classi .NET

Le librerie di classi rappresentano il concetto di [libreria condivisa](https://en.wikipedia.org/wiki/Library_%28computing%29#Shared_libraries) di .NET. Consentono di componentizzare funzionalità utili in moduli che possono essere usati da più applicazioni. Possono anche servire per caricare le funzionalità non necessarie o sconosciute all'avvio dell'applicazione. Le librerie di classi vengono descritte con il [formato di file assembly .NET](assembly/file-format.md).

È possibile usare tre tipi di librerie di classi:

* Le librerie di classi **specifiche della piattaforma**  possono accedere a tutte le API in una determinata piattaforma, ad esempio .NET Framework, Xamarin iOS, ma possono essere usate solo da app e librerie destinate a tale piattaforma.
* Le librerie di classi **portabili** possono accedere a un sottoinsieme di API e possono essere usate da app e librerie destinate a più piattaforme.
* Le librerie di classi **.NET Standard** sono una fusione del concetto di libreria specifica della piattaforma e della libreria portabile in un unico modello che offre i vantaggi di entrambi i tipi di libreria.

## <a name="platform-specific-class-libraries"></a>Librerie di classi specifiche della piattaforma

Le librerie di classi specifiche della piattaforma sono associate a una singola implementazioni di .NET, ad esempio.NET Framework in Windows, e possono pertanto dipendere in modo significativo dall'ambiente di esecuzione. Questo ambiente esporrà un set di API, come .NET e OS, gestirà ed esporrà lo stato previsto, ad esempio il registro di sistema di Windows.

Gli sviluppatori che creano librerie specifiche della piattaforma possono sfruttare completamente la piattaforma sottostante. Le librerie saranno eseguite solo su quella piattaforma specifica. I controlli piattaforma o altre forme di codice condizionale, ad esempio il singolo codice di origine del modulo per più piattaforme, non risulteranno pertanto necessari.

Le librerie specifiche della piattaforma sono state il primo tipo di libreria di classi per .NET Framework. Nonostante lo sviluppo di altre implementazioni di .NET, le librerie specifiche della piattaforma sono rimaste il tipo di libreria principale.

## <a name="portable-class-libraries"></a>Librerie di classi portabili

Le librerie portabili sono supportate su più implementazioni di .NET. Anche queste librerie possono dipendere da un tipo di ambiente di esecuzione che è tuttavia un ambiente sintetico, vale a dire un ambiente nato dall'intersezione di una serie di implementazioni di .NET concrete. Le API esposte e i presupposti della piattaforma sono pertanto un sottoinsieme di ciò che avrebbe a disposizione una libreria specifica della piattaforma.

Quando si crea una libreria portabile,è necessario scegliere una configurazione per la piattaforma. I set di piattaforme da supportare sono ad esempio .NET Framework 4.5+, Windows Phone 8.0+. Più piattaforme si decide di supportare, minore sarà il numero di API e di presupposti della piattaforma possibili e più basso sarà il denominatore comune. All'inizio questa caratteristica può creare confusione, poiché si può pensare che aver più piattaforme sia spesso la soluzione migliore. In realtà si capirà poi che le API disponibili diminuiranno se si sceglie di supportare più piattaforme.

Molti sviluppatori di librerie hanno scelto di usare le librerie portabili anziché creare librerie specifiche della piattaforma partendo da un'unica origine e applicando direttive di compilazione condizionale. Esistono [diversi approcci](https://blog.stephencleary.com/2012/11/portable-class-library-enlightenment.html) per accedere alle funzionalità specifiche della piattaforma in librerie portabili. La tecnica [bait-and-switch](https://log.paulbetts.org/the-bait-and-switch-pcl-trick/) è l'approccio più adottato.

## <a name="net-standard-class-libraries"></a>Librerie di classi .NET Standard

Le librerie .NET Standard sostituiscono le librerie specifiche della piattaforma e le librerie portatili. Sono specifiche della piattaforma nel senso che espongono tutte le funzionalità della piattaforma sottostante, ad eccezione di piattaforme sintetiche o intersezioni di piattaforme. Sono portatili nel senso che funzionano su tutte le funzioni supportate.

.NET Standard espone una serie di _contratti_ libreria. Le implementazioni di .NET devono supportare ogni contratto completamente o non lo devono supportare affatto. Ogni implementazione supporta quindi un set di contratti di .NET Standard. È quindi essenziale che ogni libreria di classi .NET Standard sia supportata sulle piattaforme che supportano le dipendenze di contratto relative.

.NET Standard non espone l'intera funzionalità di .NET Framework né questo è l'obiettivo. Espone però molte più API rispetto alle librerie di classi portatili. Altre API saranno aggiunte nel tempo.

Le piattaforme seguenti supportano le librerie di .NET Standard:

* .NET Core
* .NET Framework
* Mono
* Xamarin.iOS, Xamarin.Mac, Xamarin.Android
* Piattaforma UWP (Universal Windows Platform)
* Windows
* Windows Phone
* Windows Phone Silverlight

Per altre informazioni, vedere l'argomento [.NET Standard](net-standard.md).

## <a name="mono-class-libraries"></a>Librerie di classi Mono

Mono supporta le librerie di classi, inclusi i tre tipi di libreria descritti in precedenza. A ragione, Mono è stato spesso considerato un'implementazione multipiattaforma di Microsoft .NET Framework. In parte perché le librerie .NET Framework specifiche della piattaforma potevano essere eseguite in fase di esecuzione Mono senza modifiche o ricompilazione. Questa caratteristica esisteva prima che fossero create le librerie di classi portabili. Tali librerie risultano quindi una scelta obbligata per consentire la portabilità binaria tra .NET Framework e Mono, nonostante funzionasse solo in una direzione.
