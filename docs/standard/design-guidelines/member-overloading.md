---
title: Overload dei membri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2c84d70fb8c05dc295fc807c9a59085c47d0f455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="member-overloading"></a><span data-ttu-id="96575-102">Overload dei membri</span><span class="sxs-lookup"><span data-stu-id="96575-102">Member Overloading</span></span>
<span data-ttu-id="96575-103">Overload dei membri prevede la creazione di due o più membri sullo stesso tipo che hanno lo stesso nome ma che differiscono solo per il numero o il tipo dei parametri.</span><span class="sxs-lookup"><span data-stu-id="96575-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="96575-104">Ad esempio, di seguito, il `WriteLine` viene eseguito l'overload di metodo:</span><span class="sxs-lookup"><span data-stu-id="96575-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="96575-105">Poiché solo i metodi, costruttori e le proprietà indicizzate possono avere parametri, solo i membri possono essere sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="96575-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="96575-106">Eseguire l'overload è una delle tecniche più importanti per migliorare la leggibilità di librerie riutilizzabili usabilità e produttività.</span><span class="sxs-lookup"><span data-stu-id="96575-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="96575-107">L'overload per il numero di parametri consente di fornire versioni più semplice di costruttori e metodi.</span><span class="sxs-lookup"><span data-stu-id="96575-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="96575-108">L'overload del tipo di parametro consente di utilizzare lo stesso nome di membro per l'esecuzione di operazioni identico a un set selezionato di tipi diversi di membri.</span><span class="sxs-lookup"><span data-stu-id="96575-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="96575-109">**✓ SI** tenta di utilizzare nomi di parametro descrittivi per indicare il valore predefinito utilizzato dagli overload più breve.</span><span class="sxs-lookup"><span data-stu-id="96575-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="96575-110">**X evitare** arbitrariamente nomi dei parametri di overload.</span><span class="sxs-lookup"><span data-stu-id="96575-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="96575-111">Se un parametro in uno degli overload rappresenta lo stesso input di un parametro in un altro overload, tali parametri devono avere lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="96575-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="96575-112">**X evitare** incoerente nell'ordine dei parametri in membri di overload.</span><span class="sxs-lookup"><span data-stu-id="96575-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="96575-113">I parametri con lo stesso nome verrà visualizzato nella stessa posizione in tutti gli overload.</span><span class="sxs-lookup"><span data-stu-id="96575-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="96575-114">**✓ SI** rendere virtuale solo l'overload più lunga (se viene richiesta un'estensibilità).</span><span class="sxs-lookup"><span data-stu-id="96575-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="96575-115">Gli overload più brevi devono semplicemente chiamare tramite un overload più lungo.</span><span class="sxs-lookup"><span data-stu-id="96575-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="96575-116">**X non** utilizzare `ref` o `out` modificatori per eseguire l'overload di membri.</span><span class="sxs-lookup"><span data-stu-id="96575-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="96575-117">Alcuni linguaggi non è possibile risolvere le chiamate agli overload simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="96575-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="96575-118">Inoltre, tali overload in genere hanno una semantica completamente diversa e probabilmente non deve essere overload, ma due metodi distinti invece.</span><span class="sxs-lookup"><span data-stu-id="96575-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="96575-119">**X non** dispongono di overload con parametri nella stessa posizione e tipi simili, ma con una semantica diversa.</span><span class="sxs-lookup"><span data-stu-id="96575-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="96575-120">**✓ SI** consentire `null` da passare per gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="96575-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="96575-121">**✓ SI** utilizzare l'overload dei membri anziché definire membri con argomenti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="96575-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="96575-122">Argomenti predefiniti non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="96575-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="96575-123">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="96575-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="96575-124">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="96575-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96575-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96575-125">See Also</span></span>  
 [<span data-ttu-id="96575-126">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="96575-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="96575-127">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="96575-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
