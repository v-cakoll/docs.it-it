---
title: Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244664"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
Quando si desidera usare oggetti COM e .NET Framework nella stessa applicazione, è necessario risolvere le differenze nel modo in cui gli oggetti presenti in memoria. Un oggetto .NET Framework si trova nella memoria gestita, ovvero la memoria controllata da common language runtime e può essere spostato dal runtime in base alle esigenze. Un oggetto COM si trova nella memoria non gestita e non è previsto per spostare in un'altra posizione di memoria. Visual Studio e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono strumenti per controllare l'interazione di queste gestito e i componenti. Per altre informazioni sul codice gestito, vedere [Common Language Runtime](../../../standard/clr.md).  
  
 Oltre a usare gli oggetti COM nelle applicazioni .NET, è anche possibile usare Visual Basic per sviluppare gli oggetti accessibili da codice non gestito tramite COM.  
  
 I collegamenti in questa pagina offrono informazioni dettagliate sulle interazioni tra gli oggetti COM e .NET Framework.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM in Visual Basic, inclusi gli oggetti COM, controlli ActiveX, DLL Win32, gli oggetti gestiti ed ereditarietà degli oggetti COM.  
  
 [Errore del wrapper di interoperabilità COM](/cpp/misc/com-interop-wrapper-error)  
 Descrive le opzioni e conseguenze se il sistema di progetto non è possibile creare un wrapper di interoperabilità COM per un determinato componente.  
  
 [Interoperabilità con codice non gestito](../../../framework/interop/index.md)  
 Descrive brevemente alcuni dei problemi di interazione tra codice gestito e e vengono forniti collegamenti per approfondire l'argomento.  
  
 [Wrapper COM](../../../framework/interop/com-wrappers.md)  
 Vengono illustrati i runtime callable wrapper, che consentono al codice gestito chiamare i metodi COM, e COM callable wrapper, che consentono ai client COM di chiamare metodi oggetto .NET.  
  
 [Interoperabilità COM avanzata](../../../framework/interop/index.md)  
 Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM rispetto al wrapper, eccezioni, ereditarietà, threading, eventi, conversioni e di marshalling.  
  
 [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 Viene descritto lo strumento che è possibile usare per convertire le definizioni dei tipi presenti all'interno di una libreria dei tipi COM nelle definizioni equivalenti in un assembly di common language runtime.
