---
title: Introduzione all'interoperabilità COM
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 6c7caf266514c43e40135b33d848a688546acf1c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396779"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Introduzione all'interoperabilità COM (Visual Basic)
Il Component Object Model (COM) consente a un oggetto di esporre la funzionalità ad altri componenti e di ospitare le applicazioni. Sebbene gli oggetti COM siano stati fondamentali per la programmazione di Windows per molti anni, le applicazioni progettate per il Common Language Runtime (CLR) offrono molti vantaggi.  
  
 .NET Framework le applicazioni sostituiranno quelle sviluppate con COM. Fino ad allora, potrebbe essere necessario usare o creare oggetti COM usando Visual Studio. L'interoperabilità con COM o l' *interoperabilità COM*consente di utilizzare gli oggetti COM esistenti durante la transizione al .NET Framework al ritmo dell'utente.  
  
 Utilizzando la .NET Framework per creare componenti COM, è possibile utilizzare l'interoperabilità COM senza registrazione. In questo modo è possibile controllare la versione della DLL abilitata quando più di una versione viene installata in un computer e consente agli utenti finali di utilizzare XCOPY o FTP per copiare l'applicazione in una directory appropriata nel computer in cui è possibile eseguirla. Per altre informazioni, vedere [interoperabilità COM senza registrazione](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Codice gestito e dati  
 Il codice sviluppato per la .NET Framework viene definito *codice gestito*e contiene i metadati utilizzati da CLR. I dati utilizzati dalle applicazioni .NET Framework sono denominati *dati gestiti* perché il runtime gestisce le attività relative ai dati, ad esempio l'allocazione e il reclamo della memoria e l'esecuzione del controllo del tipo. Per impostazione predefinita, Visual Basic .NET usa codice gestito e dati, ma è possibile accedere al codice non gestito e ai dati degli oggetti COM usando gli assembly di interoperabilità, descritti più avanti in questa pagina.  
  
## <a name="assemblies"></a>Assembly  
 Un assembly è il blocco predefinito principale di un'applicazione .NET Framework. Si tratta di una raccolta di funzionalità compilata, con versione e distribuita come singola unità di implementazione contenente uno o più file. Ogni assembly contiene un manifesto dell'assembly.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Librerie dei tipi e manifesti di assembly  
 Le librerie dei tipi descrivono le caratteristiche degli oggetti COM, ad esempio i nomi dei membri e i tipi di dati. I manifesti dell'assembly eseguono la stessa funzione per .NET Framework applicazioni. Sono incluse informazioni sugli elementi seguenti:  
  
- Identità assembly, versione, impostazioni cultura e firma digitale.  
  
- File che costituiscono l'implementazione dell'assembly.  
  
- Tipi e risorse che costituiscono l'assembly. Sono inclusi quelli che vengono esportati da esso.  
  
- Dipendenze in fase di compilazione da altri assembly.  
  
- Autorizzazioni necessarie per l'esecuzione corretta dell'assembly.  
  
 Per ulteriori informazioni sugli assembly e sui manifesti dell'assembly, vedere [assembly in .NET](../../../standard/assembly/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importazione ed esportazione di librerie di tipi  
 Visual Studio contiene un'utilità, Tlbimp, che consente di importare informazioni da una libreria dei tipi in un'applicazione .NET Framework. È possibile generare librerie dei tipi dagli assembly tramite l'utilità Tlbexp.  
  
 Per informazioni su Tlbimp e Tlbexp, vedere [Tlbimp. exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md) e [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Assembly di interoperabilità  
 Gli assembly di interoperabilità sono .NET Framework assembly che eseguono il Bridge tra codice gestito e non gestito, eseguendo il mapping dei membri di oggetti COM a membri gestiti .NET Framework equivalenti. Gli assembly di interoperabilità creati da Visual Basic .NET gestiscono molti dei dettagli relativi all'utilizzo di oggetti COM, ad esempio il marshalling di interoperabilità.  
  
## <a name="interoperability-marshaling"></a>Marshalling di interoperabilità  
 Tutte le applicazioni .NET Framework condividono un set di tipi comuni che consentono l'interoperabilità degli oggetti, indipendentemente dal linguaggio di programmazione usato. I parametri e i valori restituiti degli oggetti COM utilizzano talvolta tipi di dati diversi da quelli utilizzati nel codice gestito. Il *marshalling di interoperabilità* è il processo di creazione di pacchetti di parametri e valori restituiti in tipi di dati equivalenti durante il passaggio da e verso oggetti com. Per ulteriori informazioni, vedere [marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Vedere anche

- [Interoperabilità COM](index.md)
- [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [Interoperabilità con codice non gestito](../../../framework/interop/index.md)
- [Risoluzione dei problemi relativi all'interoperabilità](troubleshooting-interoperability.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
- [Tlbimp. exe (utilità di importazione della libreria di tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp. exe (utilità di esportazione della libreria di tipi)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Marshalling di interoperabilità](../../../framework/interop/interop-marshaling.md)
- [Interoperabilità COM senza registrazione](../../../framework/interop/registration-free-com-interop.md)
