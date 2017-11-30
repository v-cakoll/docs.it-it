---
title: Supporto dello spazio dei nomi nel DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3145df6517df9db580bfcc5d67edd9d1a61f290b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-support-in-the-dom"></a><span data-ttu-id="e8915-102">Supporto dello spazio dei nomi nel DOM</span><span class="sxs-lookup"><span data-stu-id="e8915-102">Namespace Support in the DOM</span></span>
<span data-ttu-id="e8915-103">Il modello DOM XML supporta pienamente lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8915-103">The XML Document Object Model (DOM) is completely namespace-aware.</span></span> <span data-ttu-id="e8915-104">Sono supportati solo i documenti XML che supportano lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8915-104">Only namespace-aware XML documents are supported.</span></span> <span data-ttu-id="e8915-105">Il W3C (World Wide Web Consortium) specifica che lo spazio dei nomi può non essere supportato da applicazioni DOM che implementano il Livello 1, ma che è supportato dalle funzionalità di Livello 2 del DOM.</span><span class="sxs-lookup"><span data-stu-id="e8915-105">The World Wide Web Consortium (W3C) specifies that DOM applications that implement Level 1 can be non-namespace-aware, and DOM Level 2 features are namespace-aware.</span></span> <span data-ttu-id="e8915-106">Tutte le funzionalità nel DOM XML, tuttavia, supportano lo spazio dei nomi indipendentemente dal fatto che il metodo sia regolato dalla raccomandazione DOM di Livello 1 o di Livello 2.</span><span class="sxs-lookup"><span data-stu-id="e8915-106">However, all features in the XML DOM are namespace-aware, regardless if the method is from the Level 1 or Level 2 DOM Recommendation.</span></span>  
  
 <span data-ttu-id="e8915-107">Ad esempio, in un'impostazione che supporta lo spazio dei nomi, la chiamata di `setAttribute("A:b", "123")` come specificato dalla raccomandazione DOM di Livello 1, non dà luogo a un attributo con prefisso `A` e nome locale `b`,</span><span class="sxs-lookup"><span data-stu-id="e8915-107">For example, in a non-namespace-aware setting, calling `setAttribute("A:b", "123")`, as specified in the DOM Level 1 Recommendation, does not result in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="e8915-108">bensì un attributo con il valore `A:b`.</span><span class="sxs-lookup"><span data-stu-id="e8915-108">It would result in an attribute with the value `A:b`.</span></span>  
  
 <span data-ttu-id="e8915-109">In un ambiente che supporta lo spazio dei nomi, la chiamata di `setAttribute("A:b", "123")` del DOM di Livello 2 dà luogo a un attributo con prefisso `A` e nome locale `b`.</span><span class="sxs-lookup"><span data-stu-id="e8915-109">In a namespace-aware environment, the call to the DOM Level 2 `setAttribute("A:b", "123")` results in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="e8915-110">Si tratta di funzionamento di Microsoft .NET Framework DOM.</span><span class="sxs-lookup"><span data-stu-id="e8915-110">This is how the Microsoft .NET Framework DOM works.</span></span>  
  
 <span data-ttu-id="e8915-111">Quindi i metodi che accettano un nome come parametro accettano anche un prefisso per la qualifica del nome.</span><span class="sxs-lookup"><span data-stu-id="e8915-111">Therefore, for all methods that take a name parameter, these methods also take a prefix to qualify the name.</span></span> <span data-ttu-id="e8915-112">Il parametro name, ad esempio il `A:b` nel **setAttribute** metodo DOM Level 1, viene analizzato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e8915-112">The name parameter, such as the `A:b` in the **setAttribute** DOM Level 1 method, is parsed as follows:</span></span>  
  
-   <span data-ttu-id="e8915-113">Se non sono presenti caratteri di due punti (:), il nome locale viene impostato sul parametro `name` e il prefisso e NamespaceURI sono stringhe vuote.</span><span class="sxs-lookup"><span data-stu-id="e8915-113">If there are no colon (:) characters, then the local name is set to the `name` parameter, and the prefix and NamespaceURI are empty strings.</span></span>  
  
-   <span data-ttu-id="e8915-114">Se viene rilevato un carattere di due punti, il nome viene diviso in due parti, in base alla posizione del primo carattere di due punti.</span><span class="sxs-lookup"><span data-stu-id="e8915-114">If a colon is found, then the name is split into two parts based on the position of the first colon character.</span></span> <span data-ttu-id="e8915-115">Il prefisso è impostato sulla stringa prima dei due punti e il nome locale è impostato sulla stringa dopo i due punti.</span><span class="sxs-lookup"><span data-stu-id="e8915-115">The prefix is set to the string found before the colon, and local name is set to the string found after the colon.</span></span> <span data-ttu-id="e8915-116">Per i metodi che non accettano un valore NamespaceURI, quest'ultimo non è risolto e rimane impostato su una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e8915-116">For methods that do not take a NamespaceURI value, the NamespaceURI is not resolved and remains set to empty string.</span></span> <span data-ttu-id="e8915-117">In caso contrario, il NamespaceURI viene impostato sulla stringa passata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e8915-117">Otherwise, the NamespaceURI is set to the string passed to the method.</span></span> <span data-ttu-id="e8915-118">Se il prefisso è definito, il **salvare** (metodo) e **InnerXml** e **OuterXml** proprietà fail.</span><span class="sxs-lookup"><span data-stu-id="e8915-118">If the prefix is undefined, then the **Save** method and **InnerXml** and **OuterXml** properties fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8915-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8915-119">See Also</span></span>  
 [<span data-ttu-id="e8915-120">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="e8915-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
