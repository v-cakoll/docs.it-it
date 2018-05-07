---
title: Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
Quando si desidera utilizzare oggetti COM e .NET Framework nella stessa applicazione, è necessario risolvere le differenze nella modalità con cui gli oggetti presenti in memoria. Un oggetto .NET Framework si trova nella memoria gestita, la memoria controllata da common language runtime e possono essere spostati dal runtime in base alle esigenze. Un oggetto COM si trova nella memoria non gestita e non è previsto per spostare in un'altra posizione di memoria. Visual Studio e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono strumenti per controllare l'interazione di questi gestito e componenti. Per ulteriori informazioni sul codice gestito, vedere [Common Language Runtime](../../../standard/clr.md).  
  
 Oltre a utilizzare gli oggetti COM nelle applicazioni .NET, è possibile che si voglia usare Visual Basic per sviluppare gli oggetti accessibili dal codice non gestito tramite COM.  
  
 I collegamenti in questa pagina forniscono dettagli sulle interazioni tra gli oggetti COM e .NET Framework.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM in Visual Basic, inclusi gli oggetti COM, controlli ActiveX, DLL Win32, oggetti gestiti ed ereditarietà degli oggetti COM.  
  
 [Errore del wrapper di interoperabilità COM](/cpp/misc/com-interop-wrapper-error)  
 Descrive le opzioni e conseguenze se il sistema del progetto non è possibile creare un wrapper di interoperabilità COM per un determinato componente.  
  
 [Interoperabilità con codice non gestito](../../../framework/interop/index.md)  
 Descrive brevemente alcuni problemi di interazione tra codice gestito e e vengono forniti collegamenti a ulteriori informazioni.  
  
 [Wrapper COM](../../../framework/interop/com-wrappers.md)  
 Vengono descritti i runtime callable wrapper, che consentono di codice gestito di chiamare i metodi COM, e COM callable wrapper, che consentono ai client COM di chiamare metodi oggetto .NET.  
  
 [Interoperabilità COM avanzata](../../../framework/interop/index.md)  
 Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM rispetto wrapper, eccezioni, ereditarietà, threading, eventi, conversioni e marshalling.  
  
 [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 Viene descritto lo strumento che è possibile utilizzare per convertire le definizioni dei tipi presenti all'interno di una libreria dei tipi COM nelle definizioni equivalenti in un assembly di common language runtime.
