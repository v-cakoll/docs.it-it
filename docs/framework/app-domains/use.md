---
title: Uso dei domini dell'applicazione
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ebd1de46eb2757098a369b58dd9a6c0009e5b95
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742471"
---
# <a name="using-application-domains"></a>Uso dei domini dell'applicazione
I domini dell'applicazione offrono un'unità di isolamento per Common Language Runtime. Vengono creati ed eseguiti all'interno di un processo. I domini dell'applicazione vengono solitamente creati da un host di runtime, che è un'applicazione responsabile del caricamento del runtime in un processo e dell'esecuzione di codice utente all'interno di un dominio dell'applicazione. L'host di runtime crea un processo e un dominio dell'applicazione predefinito ed esegue codice gestito all'interno di esso. Gli host di runtime includono ASP.NET, Microsoft Internet Explorer e la shell di Windows.  
  
 Per la maggior parte delle applicazioni, non è necessario creare il proprio dominio dell'applicazione. L'host di runtime crea tutti i domini dell'applicazione necessari. È tuttavia possibile creare e configurare domini dell'applicazione aggiuntivi se l'applicazione necessita di isolare il codice o di usare e scaricare DLL.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare un dominio dell'applicazione](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Viene descritto come creare a livello di codice un dominio dell'applicazione.  
  
 [Procedura: Scaricare un dominio dell'applicazione](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Viene descritto come scaricare a livello di codice un dominio dell'applicazione.  
  
 [Procedura: Configurare un dominio dell'applicazione](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Viene presentata un'introduzione alla configurazione di un dominio dell'applicazione.  
  
 [Recupero di informazioni di installazione da un dominio dell'applicazione](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Viene descritto come recuperare informazioni di installazione da un dominio dell'applicazione.  
  
 [Procedura: Caricare assembly in un dominio dell'applicazione](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Viene descritto come caricare un assembly in un dominio dell'applicazione.  
  
 [Procedura: Reperire informazioni su tipo e membro da un assembly](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Viene descritto come recuperare informazioni su un assembly.  
  
 [Creazione di copie replicate di assembly](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Viene descritto come la copia shadow consente gli aggiornamenti agli assembly mentre sono in uso e come configurare la copia shadow.  
  
 [Procedura: Ricevere notifiche di eccezioni first-chance](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Viene spiegato come è possibile ricevere una notifica della generazione di un'eccezione, prima che Common Language Runtime abbia iniziato la ricerca di gestori di eccezioni.  
  
 [Risoluzione caricamenti assembly](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Vengono offerte indicazioni sull'uso dell'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> per risolvere gli errori di caricamento di assembly.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.AppDomain>  
 Rappresenta un dominio dell'applicazione. Offre metodi per creare e controllare i domini dell'applicazione.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Viene offerta una panoramica delle funzioni svolte dagli assembly.  
  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Descrive come creare, firmare e impostare attributi sugli assembly.  
  
 [Creazione di assembly e metodi dinamici](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Descrive come creare gli assembly dinamici.  
  
 [Domini dell'applicazione](../../../docs/framework/app-domains/application-domains.md)  
 Viene fornita una panoramica sui concetti di base relativi ai domini applicazione.  
  
 [Panoramica della reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.
