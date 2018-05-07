---
title: Utilizzo di oggetti dinamici (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 78b17a379ea219cc24842322703caaa9d29eeb2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Utilizzo di oggetti dinamici (Visual Basic)
Oggetti dinamici forniscono un altro modo, tranne il `Object` tipo, per l'associazione tardiva a un oggetto in fase di esecuzione. Un oggetto dinamico espone membri, ad esempio proprietà e metodi in fase di esecuzione utilizzando interfacce dinamiche che sono definite nel <xref:System.Dynamic> dello spazio dei nomi. È possibile utilizzare le classi di <xref:System.Dynamic> dello spazio dei nomi per creare gli oggetti che funzionano con strutture di dati che non corrispondono a un tipo statico o il formato. È inoltre possibile utilizzare gli oggetti dinamici definiti nei linguaggi dinamici, ad esempio IronPython e IronRuby. Per esempi che illustrano come creare oggetti dinamici o utilizzare un oggetto dinamico definito in un linguaggio dinamico, vedere [procedura dettagliata: creazione e l'uso oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic l'associazione a oggetti dal dynamic language runtime e linguaggi dinamici, ad esempio IronPython e IronRuby utilizzando il <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaccia. Esempi di classi che implementano il `IDynamicMetaObjectProvider` interfaccia sono il <xref:System.Dynamic.DynamicObject> e <xref:System.Dynamic.ExpandoObject> classi.  
  
 Se viene eseguita una chiamata con associazione tardiva a un oggetto che implementa il `IDynamicMetaObjectProvider` interfaccia, Visual Basic viene associato a un oggetto dinamico di tramite tale interfaccia. Se viene eseguita una chiamata con associazione tardiva a un oggetto che non implementa il `IDynamicMetaObjectProvider` interfaccia, oppure se la chiamata al `IDynamicMetaObjectProvider` interfaccia ha esito negativo, Visual Basic associa all'oggetto utilizzando le funzionalità di associazione tardiva del runtime di Visual Basic.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [Procedura dettagliata: Creazione e utilizzo di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
