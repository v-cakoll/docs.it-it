---
title: 'Procedura: Dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: e4132f51f4dd85ad964042d05f7c5bc0a2e6e3cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826626"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="61d16-102">Procedura: Dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61d16-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="61d16-103">Esistono diversi casi quando è importante che un'applicazione mantenere ridotto l'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="61d16-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="61d16-104">Eventi personalizzati consentono all'applicazione di utilizzo della memoria solo per gli eventi che gestisce.</span><span class="sxs-lookup"><span data-stu-id="61d16-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="61d16-105">Per impostazione predefinita, quando una classe dichiara un evento, il compilatore alloca memoria per un campo archiviare le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="61d16-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="61d16-106">Se una classe dispone di molti eventi inutilizzati, inutilmente occupano memoria.</span><span class="sxs-lookup"><span data-stu-id="61d16-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="61d16-107">Invece di usare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile utilizzare gli eventi personalizzati per gestire l'utilizzo della memoria più attentamente.</span><span class="sxs-lookup"><span data-stu-id="61d16-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61d16-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="61d16-108">Example</span></span>  
 <span data-ttu-id="61d16-109">In questo esempio, la classe usa un'istanza del <xref:System.ComponentModel.EventHandlerList> (classe), archiviate nel `Events` campo, per archiviare le informazioni sugli eventi in uso.</span><span class="sxs-lookup"><span data-stu-id="61d16-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="61d16-110">Il <xref:System.ComponentModel.EventHandlerList> è una classe di elenco ottimizzata progettata per contenere i delegati.</span><span class="sxs-lookup"><span data-stu-id="61d16-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="61d16-111">Tutti gli eventi della classe utilizzano il `Events` campo per tenere traccia di quali metodi sono la gestione di ogni evento.</span><span class="sxs-lookup"><span data-stu-id="61d16-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="61d16-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61d16-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="61d16-113">Eventi</span><span class="sxs-lookup"><span data-stu-id="61d16-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="61d16-114">Procedura: Dichiarare eventi personalizzati per evitare il blocco</span><span class="sxs-lookup"><span data-stu-id="61d16-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
