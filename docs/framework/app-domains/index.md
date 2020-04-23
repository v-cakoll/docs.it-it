---
title: Programmazione con i domini applicazione e gli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 3f66eacaf30f8001cdbf3a486e5ce1c878712e2f
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644279"
---
# <a name="programming-with-application-domains-and-assemblies"></a>Programmazione con i domini applicazione e gli assembly

Gli host come Microsoft Internet Explorer, ASP.NET e la shell di Windows caricano Common Language Runtime in un processo, creano un [dominio dell'applicazione](application-domains.md) in tale processo e quindi caricano ed eseguono codice dell'utente in tale dominio dell'applicazione quando eseguono un'applicazione .NET Framework. Nella maggior parte dei casi, non è necessario occuparsi della creazione dei domini dell'applicazione e del caricamento di assembly all'interno degli stessi, perché è l'host di runtime a eseguire tali attività.  
  
Tuttavia, se si sta creando un'applicazione che ospita Common Language Runtime, strumenti o codice che si vogliono scaricare a livello di codice o componenti modulari che possono essere scaricati e ricaricati in tempo reale, si creano anche domini dell'applicazione personalizzati. Anche se non si sta creando un host di runtime, questa sezione fornisce importanti informazioni su come utilizzare i domini dell'applicazione e gli assembly caricati al loro interno.  
  
## <a name="in-this-section"></a>Contenuto della sezione  

[Argomenti relativi alle procedure per domini applicazione e assembly](application-domains-and-assemblies-how-to-topics.md)  
Fornisce i collegamenti a tutte le procedure contenute nella documentazione sui concetti relativi alla programmazione con domini dell'applicazione e assembly.  
  
[Uso dei domini dell'applicazione](use.md)  
Fornisce esempi di creazione, configurazione e uso dei domini dell'applicazione.  
  
[Programmazione con gli assembly](../../standard/assembly/index.md)  
Descrive come creare, firmare e impostare attributi sugli assembly.  
  
## <a name="related-sections"></a>Sezioni correlate  

[Creazione di assembly e metodi dinamici](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
Descrive come creare gli assembly dinamici.  
  
[Assembly in .NET](../../standard/assembly/index.md)  
Viene fornita una panoramica sui concetti di base relativi agli assembly.  
  
[Domini applicazione](application-domains.md)  
Viene fornita una panoramica sui concetti di base relativi ai domini applicazione.  
  
[Panoramica della reflection](../reflection-and-codedom/reflection.md)  
Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.
