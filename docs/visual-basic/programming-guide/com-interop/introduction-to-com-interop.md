---
title: Introduzione all'interoperabilità COM (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 68e750fccd988a9cf7e08b4e7169bd2385d48e1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734857"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Introduzione all'interoperabilità COM (Visual Basic)
Il modello COM (Component Object) consente a un oggetto di esporre le proprie funzionalità agli altri componenti e alle applicazioni host. Anche se gli oggetti COM sono state fondamentali per Windows di programmazione per molti anni, le applicazioni progettate per common language runtime (CLR) offrono numerosi vantaggi.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Infine, le applicazioni sostituiranno quelle sviluppate con COM. Fino ad allora, è possibile usare o creare oggetti COM con Visual Studio. Interoperabilità COM, oppure *interoperabilità COM*, consente di usare oggetti COM esistenti durante la fase di transizione per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] a proprio piacimento.  
  
 Tramite il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] per creare componenti COM, è possibile usare l'interoperabilità COM senza registrazione. Ciò consente di controllare la versione della DLL è abilitata quando più di una versione viene installata in un computer e consente agli utenti finali di usare XCOPY o FTP per copiare l'applicazione in una directory appropriata nel computer in cui può essere eseguito. Per altre informazioni, vedere [interoperabilità COM senza registrazione](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Il codice gestito e dati  
 Il codice sviluppato per le [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] è detta *codice gestito*e contiene i metadati usati da CLR. I dati utilizzati dalle [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applicazioni viene chiamato *managed data* perché il runtime gestisce le attività correlate ai dati ad esempio l'allocazione e il recupero della memoria e dei tipi di controllo. Per impostazione predefinita, Visual Basic .NET Usa codice gestito e i dati, ma è possibile accedere a codice non gestito e i dati di oggetti COM mediante assembly di interoperabilità (descritto più avanti in questa pagina).  
  
## <a name="assemblies"></a>Assembly  
 Un assembly è il principale blocco predefinito di un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dell'applicazione. È una raccolta di funzionalità che vengono compilate, con controllo delle versioni e distribuiti come unità singola implementazione che contiene uno o più file. Ogni assembly contiene un manifesto dell'assembly.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Manifesti dell'Assembly e le librerie dei tipi  
 Librerie dei tipi descrivono le caratteristiche degli oggetti COM, ad esempio i nomi dei membri e tipi di dati. Manifesti dell'assembly eseguano la stessa funzione per [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applicazioni. Includono le informazioni seguenti:  
  
-   Identità dell'assembly, versione, impostazioni cultura e firma digitale.  
  
-   File che compongono l'implementazione dell'assembly.  
  
-   Tipi e risorse che compongono l'assembly. Sono inclusi quelli che vengono esportati da quest'ultimo.  
  
-   Dipendenze in fase di compilazione da altri assembly.  
  
-   Autorizzazioni necessarie per l'assembly da eseguire in modo corretto.  
  
 Per altre informazioni sugli assembly e manifesti dell'assembly, vedere [gli assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importazione ed esportazione delle librerie dei tipi  
 Visual Studio include un'utilità, Tlbimp, che consente di importare le informazioni da una libreria dei tipi in un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dell'applicazione. È possibile generare le librerie dei tipi da assembly utilizzando l'utilità Tlbexp.  
  
 Per informazioni su Tlbimp e Tlbexp, vedere [(tipo di libreria utilità di importazione) Tlbimp.exe](../../../framework/tools/tlbimp-exe-type-library-importer.md) e [Tlbexp.exe (Type Library Exporter)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Assembly di interoperabilità  
 Sono gli assembly di interoperabilità [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli assembly che bridge between gestito e codice, membri dell'oggetto COM mapping equivalente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] membri gestiti. Gli assembly di interoperabilità creati da Visual Basic .NET gestiscono molti dei dettagli relativi all'utilizzo con oggetti COM, ad esempio il marshalling di interoperabilità.  
  
## <a name="interoperability-marshaling"></a>Il marshalling di interoperabilità  
 Tutti i [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applicazioni condividono un set di tipi comuni che consentono l'interoperabilità di oggetti, indipendentemente dal linguaggio di programmazione usato. I parametri e valori restituiti di oggetti COM in alcuni casi utilizzano tipi di dati che differiscono da quelli usati nel codice gestito. *Il marshalling di interoperabilità* è il processo di creazione dei pacchetti parametri e valori restituiti nei tipi di dati equivalente durante lo spostamento da e verso oggetti COM. Per altre informazioni, vedere [marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Vedere anche

- [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Interoperabilità con codice non gestito](../../../framework/interop/index.md)
- [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md)
- [Interoperabilità COM senza registrazione](../../../framework/interop/registration-free-com-interop.md)
