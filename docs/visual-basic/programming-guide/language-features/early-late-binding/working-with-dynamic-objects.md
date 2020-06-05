---
title: Utilizzo di oggetti dinamici
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 13b7c80537700c934dbb807b0f264218357088ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405170"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Utilizzo di oggetti dinamici (Visual Basic)
Gli oggetti dinamici forniscono un altro modo, ad eccezione del `Object` tipo, per eseguire il binding tardivo a un oggetto in fase di esecuzione. Un oggetto dinamico espone membri come proprietà e metodi in fase di esecuzione utilizzando interfacce dinamiche definite nello <xref:System.Dynamic> spazio dei nomi. È possibile utilizzare le classi nello <xref:System.Dynamic> spazio dei nomi per creare oggetti che funzionano con strutture di dati che non corrispondono a un tipo o un formato statico. È inoltre possibile utilizzare gli oggetti dinamici definiti in linguaggi dinamici, ad esempio IronPython e IronRuby. Per esempi che illustrano come creare oggetti dinamici o usare un oggetto dinamico definito in un linguaggio dinamico, vedere [procedura dettagliata: creazione e utilizzo di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> o <xref:System.Dynamic.ExpandoObject> .  
  
 Visual Basic viene associato a oggetti da Dynamic Language Runtime e linguaggi dinamici, ad esempio IronPython e IronRuby usando l' <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaccia. Esempi di classi che implementano l' `IDynamicMetaObjectProvider` interfaccia sono <xref:System.Dynamic.DynamicObject> le <xref:System.Dynamic.ExpandoObject> classi e.  
  
 Se viene eseguita una chiamata ad associazione tardiva a un oggetto che implementa l' `IDynamicMetaObjectProvider` interfaccia, Visual Basic viene associato all'oggetto dinamico mediante tale interfaccia. Se viene eseguita una chiamata ad associazione tardiva a un oggetto che non implementa l' `IDynamicMetaObjectProvider` interfaccia o se la chiamata all'interfaccia ha `IDynamicMetaObjectProvider` esito negativo, Visual Basic viene associato all'oggetto utilizzando le funzionalità di associazione tardiva del runtime di Visual Basic.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Procedura dettagliata: creazione e utilizzo di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Associazione anticipata e tardiva](index.md)
