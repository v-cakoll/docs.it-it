---
title: Introduzione all'interoperabilità COM (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5a13fabd729218dc2a980b9c63e153d17a140cce
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="introduction-to-com-interop-visual-basic"></a>Introduzione all'interoperabilità COM (Visual Basic)
Il modello COM (Component Object) consente a un oggetto esporne la funzionalità per gli altri componenti e applicazioni host. Mentre gli oggetti COM sono stati fondamentali della programmazione per molti anni Windows, le applicazioni progettate per common language runtime (CLR) offrono numerosi vantaggi.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Infine, le applicazioni sostituiranno quelle sviluppate con COM. Fino ad allora, è possibile utilizzare o creare oggetti COM con Visual Studio. Interoperabilità COM, o *l'interoperabilità COM*, consente di utilizzare gli oggetti COM esistenti durante la fase di transizione per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] con gradualità.  
  
 Tramite il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] per creare componenti COM, è possibile utilizzare l'interoperabilità COM senza registrazione. Ciò consente di controllare la versione della DLL è abilitato quando sono installato in un computer più versioni e consente agli utenti finali di utilizzare XCOPY o FTP per copiare l'applicazione in una directory appropriata nel computer in cui può essere eseguito. Per ulteriori informazioni, vedere [interoperabilità COM senza registrazione](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Il codice gestito e dati  
 Il codice sviluppato per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] è detto *codice gestito*e contiene i metadati utilizzati da CLR. I dati utilizzati dalle [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applicazioni viene chiamato *dati gestiti* perché il runtime gestisce le attività correlate ai dati, ad esempio l'allocazione e il recupero della memoria e dei tipi di controllo. Per impostazione predefinita, Visual Basic .NET utilizza dati e codice gestito, ma è possibile accedere a codice non gestito e i dati di oggetti COM tramite assembly di interoperabilità (descritto più avanti in questa pagina).  
  
## <a name="assemblies"></a>Assembly  
 Un assembly costituisce la base di un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dell'applicazione. È una raccolta di funzionalità che vengono compilate, con controllo delle versioni e distribuiti come unità singola implementazione contenente uno o più file. Ogni assembly contiene un manifesto dell'assembly.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Librerie dei tipi e i manifesti dell'Assembly  
 Librerie dei tipi descrivono le caratteristiche di oggetti COM, ad esempio i nomi dei membri e tipi di dati. Manifesti dell'assembly eseguono la stessa funzione per [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applicazioni. Sono incluse le seguenti informazioni:  
  
-   Identità dell'assembly, versione, impostazioni cultura e firma digitale.  
  
-   File che costituiscono l'implementazione dell'assembly.  
  
-   Tipi e risorse che compongono l'assembly. Sono inclusi quelli che vengono esportati da esso.  
  
-   In fase di compilazione dipendenze da altri assembly.  
  
-   Autorizzazioni necessarie per l'assembly venga eseguita correttamente.  
  
 Per ulteriori informazioni sugli assembly e manifesti dell'assembly, vedere [assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importazione ed esportazione di librerie dei tipi  
 Visual Studio include un'utilità, Tlbimp, che consente di importare le informazioni da una libreria dei tipi in un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dell'applicazione. È possibile generare le librerie dei tipi da assembly tramite l'utilità Tlbexp.  
  
 Per informazioni su Tlbimp e Tlbexp, vedere [Tlbimp.exe (utilità di importazione di tipo libreria)](../../../framework/tools/tlbimp-exe-type-library-importer.md) e [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Assembly di interoperabilità  
 Assembly di interoperabilità sono [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli assembly che bridge tra gestito e codice, membri dell'oggetto COM mapping equivalente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] membri gestiti. Assembly di interoperabilità creati da Visual Basic .NET gestiscono molti dei dettagli relativi all'utilizzo con oggetti COM, ad esempio il marshalling di interoperabilità.  
  
## <a name="interoperability-marshaling"></a>Il marshalling di interoperabilità  
 Tutti [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applicazioni condividono un set di tipi comuni che consentono l'interoperabilità tra gli oggetti, indipendentemente dal linguaggio di programmazione utilizzato. I parametri e valori restituiti di oggetti COM talvolta utilizzano tipi di dati diversi da quelli usati nel codice gestito. *Il marshalling di interoperabilità* è il processo di creazione del pacchetto parametri e valori restituiti nei tipi di dati equivalente durante lo spostamento da e verso oggetti COM. Per ulteriori informazioni, vedere [marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Interoperabilità con codice non gestito](../../../framework/interop/index.md)  
 [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md)  
 [Interoperabilità COM senza registrazione](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
