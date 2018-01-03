---
title: "Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c84143e22f33f572447c50e33559a52469b181a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
Quando si desidera utilizzare oggetti COM e .NET Framework nella stessa applicazione, è necessario risolvere le differenze nella modalità con cui gli oggetti presenti in memoria. Un oggetto .NET Framework si trova nella memoria gestita, la memoria controllata da common language runtime e possono essere spostati dal runtime in base alle esigenze. Un oggetto COM si trova nella memoria non gestita e non è previsto per spostare in un'altra posizione di memoria. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono strumenti per controllare l'interazione di questi gestito e componenti. Per ulteriori informazioni sul codice gestito, vedere [Common Language Runtime](../../../standard/clr.md).  
  
 Oltre a utilizzare oggetti COM nelle applicazioni .NET, è anche possibile utilizzare [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per sviluppare gli oggetti accessibili dal codice non gestito tramite COM.  
  
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
