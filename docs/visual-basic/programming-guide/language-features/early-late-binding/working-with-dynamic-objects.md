---
title: Utilizzo di oggetti dinamici
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345169"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Utilizzo di oggetti dinamici (Visual Basic)
Gli oggetti dinamici forniscono un altro modo, ad eccezione del tipo `Object`, per eseguire il binding tardivo a un oggetto in fase di esecuzione. Un oggetto dinamico espone membri come proprietà e metodi in fase di esecuzione utilizzando interfacce dinamiche definite nello spazio dei nomi <xref:System.Dynamic>. È possibile utilizzare le classi nello spazio dei nomi <xref:System.Dynamic> per creare oggetti che funzionano con strutture di dati che non corrispondono a un tipo o un formato statico. È inoltre possibile utilizzare gli oggetti dinamici definiti in linguaggi dinamici, ad esempio IronPython e IronRuby. Per esempi che illustrano come creare oggetti dinamici o usare un oggetto dinamico definito in un linguaggio dinamico, vedere [procedura dettagliata: creazione e uso di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>o <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic viene associato a oggetti da Dynamic Language Runtime e linguaggi dinamici, ad esempio IronPython e IronRuby usando l'interfaccia <xref:System.Dynamic.IDynamicMetaObjectProvider>. Esempi di classi che implementano l'interfaccia `IDynamicMetaObjectProvider` sono le classi <xref:System.Dynamic.DynamicObject> e <xref:System.Dynamic.ExpandoObject>.  
  
 Se viene eseguita una chiamata ad associazione tardiva a un oggetto che implementa l'interfaccia `IDynamicMetaObjectProvider`, Visual Basic viene associato all'oggetto dinamico mediante tale interfaccia. Se viene eseguita una chiamata ad associazione tardiva a un oggetto che non implementa l'interfaccia `IDynamicMetaObjectProvider` o se la chiamata all'interfaccia `IDynamicMetaObjectProvider` ha esito negativo, Visual Basic viene associata all'oggetto utilizzando le funzionalità di associazione tardiva del runtime di Visual Basic.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Procedura dettagliata: Creazione e utilizzo di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
