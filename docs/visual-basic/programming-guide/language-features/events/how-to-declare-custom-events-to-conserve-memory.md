---
title: 'Procedura: dichiarare eventi personalizzati per proteggere la memoria'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: c9a049d3f15d5620152f064888a97bd0be5d46b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405131"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="21b67-102">Procedura: dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21b67-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="21b67-103">In alcuni casi è importante che un'applicazione mantenga l'utilizzo di memoria basso.</span><span class="sxs-lookup"><span data-stu-id="21b67-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="21b67-104">Gli eventi personalizzati consentono all'applicazione di usare la memoria solo per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="21b67-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="21b67-105">Per impostazione predefinita, quando una classe dichiara un evento, il compilatore alloca memoria per un campo per archiviare le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="21b67-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="21b67-106">Se una classe dispone di molti eventi non utilizzati, inutilmente si occupino di memoria.</span><span class="sxs-lookup"><span data-stu-id="21b67-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="21b67-107">Invece di usare l'implementazione predefinita di eventi forniti da Visual Basic, è possibile usare gli eventi personalizzati per gestire l'utilizzo della memoria con maggiore attenzione.</span><span class="sxs-lookup"><span data-stu-id="21b67-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21b67-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="21b67-108">Example</span></span>  
 <span data-ttu-id="21b67-109">In questo esempio, la classe usa un'istanza della <xref:System.ComponentModel.EventHandlerList> classe, archiviata nel `Events` campo, per archiviare le informazioni sugli eventi in uso.</span><span class="sxs-lookup"><span data-stu-id="21b67-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="21b67-110">La <xref:System.ComponentModel.EventHandlerList> classe è una classe di elenco ottimizzata progettata per ospitare delegati.</span><span class="sxs-lookup"><span data-stu-id="21b67-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="21b67-111">Tutti gli eventi nella classe usano il `Events` campo per tenere traccia dei metodi che gestiscono ogni evento.</span><span class="sxs-lookup"><span data-stu-id="21b67-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="21b67-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21b67-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="21b67-113">Events</span><span class="sxs-lookup"><span data-stu-id="21b67-113">Events</span></span>](index.md)
- [<span data-ttu-id="21b67-114">Procedura: dichiarare eventi personalizzati per evitare il blocco</span><span class="sxs-lookup"><span data-stu-id="21b67-114">How to: Declare Custom Events To Avoid Blocking</span></span>](how-to-declare-custom-events-to-avoid-blocking.md)
