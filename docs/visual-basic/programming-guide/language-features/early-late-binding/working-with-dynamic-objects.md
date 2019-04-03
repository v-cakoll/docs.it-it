---
title: Utilizzo di oggetti dinamici (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: ea7d7aae1cd79a0243a9c721b5e3958fba82f84f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832073"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Utilizzo di oggetti dinamici (Visual Basic)
Oggetti dinamici rappresentano un metodo alternativo, diverso dal `Object` tipo, per eseguire l'associazione tardiva a un oggetto in fase di esecuzione. Un oggetto dinamico espone i membri, ad esempio proprietà e metodi in fase di esecuzione usando le interfacce dinamiche definiti nel <xref:System.Dynamic> dello spazio dei nomi. È possibile usare le classi di <xref:System.Dynamic> dello spazio dei nomi per creare gli oggetti che funzionano con strutture di dati che non corrispondono a un tipo o formato statico. È anche possibile usare gli oggetti dinamici definiti in linguaggi dinamici quali IronRuby e IronPython. Per esempi che illustrano come creare oggetti dinamici o usare un oggetto dinamico definito in un linguaggio dinamico, vedere [procedura dettagliata: Creazione e utilizzo di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.  
  
 Associa a oggetti Visual Basic dal runtime di linguaggio dinamico e linguaggi dinamici quali IronRuby e IronPython utilizzando il <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaccia. Esempi di classi che implementano il `IDynamicMetaObjectProvider` interfaccia sono il <xref:System.Dynamic.DynamicObject> e <xref:System.Dynamic.ExpandoObject> classi.  
  
 Se viene eseguita una chiamata con associazione tardiva a un oggetto che implementa il `IDynamicMetaObjectProvider` interfaccia, Visual Basic viene associato all'oggetto dinamica tramite tale interfaccia. Se viene eseguita una chiamata con associazione tardiva a un oggetto che non implementa il `IDynamicMetaObjectProvider` interfaccia, oppure se la chiamata al `IDynamicMetaObjectProvider` interfaccia ha esito negativo, Visual Basic si associa all'oggetto utilizzando le funzionalità di associazione tardiva di runtime di Visual Basic.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Procedura dettagliata: Creazione e uso di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
