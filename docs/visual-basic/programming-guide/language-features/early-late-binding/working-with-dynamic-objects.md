---
title: Utilizzo di oggetti dinamici (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d1e1c4f7338daad0f1101f6e886eba6c37316b0e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="93a50-102">Utilizzo di oggetti dinamici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93a50-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="93a50-103">Oggetti dinamici forniscono diverso da un altro modo, il `Object` tipo, l'associazione tardiva a un oggetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="93a50-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="93a50-104">Un oggetto dinamico espone membri, ad esempio proprietà e metodi in fase di esecuzione utilizzando interfacce dinamiche che vengono definite nel <xref:System.Dynamic>dello spazio dei nomi.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="93a50-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="93a50-105">È possibile utilizzare le classi di <xref:System.Dynamic>dello spazio dei nomi per creare gli oggetti che funzionano con strutture di dati che non corrispondono a un formato o il tipo statico.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="93a50-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="93a50-106">È inoltre possibile utilizzare gli oggetti dinamici definiti in linguaggi dinamici quali IronPython e IronRuby.</span><span class="sxs-lookup"><span data-stu-id="93a50-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="93a50-107">Per esempi che illustrano come creare oggetti dinamici o utilizzare un oggetto dinamico definito in un linguaggio dinamico, vedere [procedura dettagliata: creazione e l'uso oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="93a50-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="93a50-108">associazione a oggetti dal runtime di linguaggio dinamico e linguaggi dinamici quali IronPython e IronRuby tramite il <xref:System.Dynamic.IDynamicMetaObjectProvider>interfaccia.</xref:System.Dynamic.IDynamicMetaObjectProvider></span><span class="sxs-lookup"><span data-stu-id="93a50-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="93a50-109">Esempi di classi che implementano il `IDynamicMetaObjectProvider` interfaccia sono il <xref:System.Dynamic.DynamicObject>e <xref:System.Dynamic.ExpandoObject>classi.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="93a50-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="93a50-110">Se viene effettuata una chiamata ad associazione tardiva a un oggetto che implementa il `IDynamicMetaObjectProvider` interfaccia [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] associata all'oggetto dinamico utilizzando tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="93a50-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="93a50-111">Se viene effettuata una chiamata ad associazione tardiva a un oggetto che implementa il `IDynamicMetaObjectProvider` interfaccia, o se la chiamata al `IDynamicMetaObjectProvider` interfaccia ha esito negativo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] associata all'oggetto utilizzando le funzionalità di associazione tardiva del [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime.</span><span class="sxs-lookup"><span data-stu-id="93a50-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a50-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93a50-112">See Also</span></span>  
 <span data-ttu-id="93a50-113"><xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="93a50-113"><xref:System.Dynamic.DynamicObject></span></span>   
 <span data-ttu-id="93a50-114"><xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject></span><span class="sxs-lookup"><span data-stu-id="93a50-114"><xref:System.Dynamic.ExpandoObject></span></span>   
<span data-ttu-id="93a50-115"> [Procedura dettagliata: Creazione e utilizzo di oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span><span class="sxs-lookup"><span data-stu-id="93a50-115"> [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span></span>  
<span data-ttu-id="93a50-116"> [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="93a50-116"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
