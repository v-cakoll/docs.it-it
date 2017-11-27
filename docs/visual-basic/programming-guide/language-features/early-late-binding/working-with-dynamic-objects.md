---
title: Utilizzo di oggetti dinamici (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da70c1e4c7398ad46d48c85b62ab884675bd1a73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="65a31-102">Utilizzo di oggetti dinamici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65a31-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="65a31-103">Oggetti dinamici forniscono un altro modo, tranne il `Object` tipo, per l'associazione tardiva a un oggetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="65a31-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="65a31-104">Un oggetto dinamico espone membri, ad esempio proprietà e metodi in fase di esecuzione utilizzando interfacce dinamiche che sono definite nel <xref:System.Dynamic> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="65a31-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="65a31-105">È possibile utilizzare le classi di <xref:System.Dynamic> dello spazio dei nomi per creare gli oggetti che funzionano con strutture di dati che non corrispondono a un tipo statico o il formato.</span><span class="sxs-lookup"><span data-stu-id="65a31-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="65a31-106">È inoltre possibile utilizzare gli oggetti dinamici definiti nei linguaggi dinamici, ad esempio IronPython e IronRuby.</span><span class="sxs-lookup"><span data-stu-id="65a31-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="65a31-107">Per esempi che illustrano come creare oggetti dinamici o utilizzare un oggetto dinamico definito in un linguaggio dinamico, vedere [procedura dettagliata: creazione e l'uso oggetti dinamici](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, o <xref:System.Dynamic.ExpandoObject>.</span><span class="sxs-lookup"><span data-stu-id="65a31-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="65a31-108">l'associazione a oggetti dal dynamic language runtime e linguaggi dinamici, ad esempio IronPython e IronRuby utilizzando il <xref:System.Dynamic.IDynamicMetaObjectProvider> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65a31-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="65a31-109">Esempi di classi che implementano il `IDynamicMetaObjectProvider` interfaccia sono il <xref:System.Dynamic.DynamicObject> e <xref:System.Dynamic.ExpandoObject> classi.</span><span class="sxs-lookup"><span data-stu-id="65a31-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="65a31-110">Se viene eseguita una chiamata di associazione tardiva a un oggetto che implementa il `IDynamicMetaObjectProvider` interfaccia [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] associa all'oggetto dinamico utilizzando tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65a31-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="65a31-111">Se viene effettuata una chiamata ad associazione tardiva a un oggetto che implementa il `IDynamicMetaObjectProvider` interfaccia, o se la chiamata al `IDynamicMetaObjectProvider` interfaccia ha esito negativo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] associa all'oggetto utilizzando le funzionalità di associazione tardiva del [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime.</span><span class="sxs-lookup"><span data-stu-id="65a31-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a31-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65a31-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [<span data-ttu-id="65a31-113">Procedura dettagliata: Creazione e utilizzo di oggetti dinamici</span><span class="sxs-lookup"><span data-stu-id="65a31-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [<span data-ttu-id="65a31-114">Associazione anticipata e tardiva</span><span class="sxs-lookup"><span data-stu-id="65a31-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
