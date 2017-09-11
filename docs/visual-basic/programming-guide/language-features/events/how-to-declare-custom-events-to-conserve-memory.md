---
title: 'Procedura: dichiarare eventi personalizzati per risparmiare memoria (Visual Basic) | Documenti di Microsoft'
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
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
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
ms.openlocfilehash: 130cbda875d6a56f826aefea341d233ea4b3731d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="9f8f1-102">Procedura: dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f8f1-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="9f8f1-103">Esistono diverse circostanze quando è importante che un'applicazione mantenere l'utilizzo della memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="9f8f1-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="9f8f1-104">Gli eventi personalizzati consentono all'applicazione di utilizzare memoria solo per gli eventi che gestisce.</span><span class="sxs-lookup"><span data-stu-id="9f8f1-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="9f8f1-105">Per impostazione predefinita, quando una classe dichiara un evento, il compilatore alloca memoria per un campo archiviare le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="9f8f1-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="9f8f1-106">Se una classe dispone di molti eventi inutilizzati, essi consumano inutilmente memoria.</span><span class="sxs-lookup"><span data-stu-id="9f8f1-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="9f8f1-107">Anziché utilizzare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile utilizzare gli eventi personalizzati per gestire più attentamente l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="9f8f1-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f8f1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f8f1-108">Example</span></span>  
 <span data-ttu-id="9f8f1-109">In questo esempio, la classe utilizza un'istanza di <xref:System.ComponentModel.EventHandlerList>(classe), archiviati nel `Events` campo, per archiviare le informazioni sugli eventi in uso.</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="9f8f1-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="9f8f1-110">Il <xref:System.ComponentModel.EventHandlerList>è una classe elenco ottimizzata progettata per contenere delegati.</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="9f8f1-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="9f8f1-111">Tutti gli eventi della classe utilizzano il `Events` campo per tenere traccia di quali metodi stanno gestendo ciascun evento.</span><span class="sxs-lookup"><span data-stu-id="9f8f1-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 <span data-ttu-id="9f8f1-112">[!code-vb[VbVbalrEvents&#22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9f8f1-112">[!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8f1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f8f1-113">See Also</span></span>  
 <span data-ttu-id="9f8f1-114"><xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="9f8f1-114"><xref:System.ComponentModel.EventHandlerList></span></span>   
<span data-ttu-id="9f8f1-115"> [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f8f1-115"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="9f8f1-116"> [Procedura: Dichiarare eventi personalizzati per evitare il blocco](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="9f8f1-116"> [How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span></span>
