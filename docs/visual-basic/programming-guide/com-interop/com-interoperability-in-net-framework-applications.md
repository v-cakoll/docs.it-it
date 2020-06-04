---
title: Interoperabilità COM nelle applicazioni .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET Framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 377958a21886fe0257633ea19417f9a19bd51ff3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396869"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)

Quando si desidera utilizzare oggetti COM e .NET Framework oggetti nella stessa applicazione, è necessario risolvere le differenze nella modalità di esistenza degli oggetti in memoria. Un oggetto .NET Framework si trova in managed memory, ovvero la memoria controllata dal Common Language Runtime, e può essere spostato dal runtime in base alle esigenze. Un oggetto COM si trova nella memoria non gestita e non prevede lo spostamento in un'altra posizione di memoria. Visual Studio e il .NET Framework forniscono strumenti per controllare l'interazione di questi componenti gestiti e non gestiti. Per altre informazioni sul codice gestito, vedere [Common Language Runtime](../../../standard/clr.md).

Oltre a usare gli oggetti COM nelle applicazioni .NET, è anche possibile usare Visual Basic per sviluppare oggetti accessibili da codice non gestito tramite COM.

I collegamenti in questa pagina forniscono informazioni dettagliate sulle interazioni tra gli oggetti COM e .NET Framework.

## <a name="related-sections"></a>Sezioni correlate

| | |
|---------|---------|
| [Interoperabilità COM](index.md) | Vengono forniti collegamenti ad argomenti relativi all'interoperabilità COM in Visual Basic, inclusi oggetti COM, controlli ActiveX, dll Win32, oggetti gestiti ed ereditarietà di oggetti COM. |
| [Interoperabilità con codice non gestito](../../../framework/interop/index.md) | Descrive brevemente alcuni problemi di interazione tra codice gestito e non gestito e fornisce collegamenti per ulteriori studi. |
| [Wrapper COM](../../../standard/native-interop/com-wrappers.md) | Vengono illustrati i Runtime Callable Wrapper che consentono al codice gestito di chiamare i metodi COM e COM Callable Wrapper che consentono ai client COM di chiamare i metodi dell'oggetto .NET. |
| [Interoperabilità COM avanzata](../../../framework/interop/index.md) | Vengono forniti collegamenti ad argomenti relativi all'interoperabilità COM rispetto a wrapper, eccezioni, ereditarietà, Threading, eventi, conversioni e marshalling. |
| [Tlbimp. exe (utilità di importazione della libreria di tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md) | Viene illustrato lo strumento che è possibile utilizzare per convertire le definizioni dei tipi presenti in una libreria dei tipi COM in definizioni equivalenti in un assembly Common Language Runtime. |
