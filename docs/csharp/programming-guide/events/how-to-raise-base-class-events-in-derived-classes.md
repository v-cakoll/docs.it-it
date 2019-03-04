---
title: 'Procedura: Generare eventi della classe di base in classi derivate - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: bc968ea9c6f60ea6efda807bf254f595c61f8d4a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976083"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="f41ae-102">Procedura: Generare eventi della classe di base in classi derivate (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f41ae-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="f41ae-103">L'esempio seguente illustra il metodo standard di dichiarazione degli eventi in una classe base in modo che possano essere generati anche dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="f41ae-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="f41ae-104">Questo modello è usato spesso nelle classi Windows Forms nella libreria di classi [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f41ae-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="f41ae-105">Quando si crea una classe che può essere usata come classe base di altre classi, è necessario tenere presente che gli eventi sono un tipo speciale di delegati che possono essere richiamati solo dall'interno della classe che li ha dichiarati.</span><span class="sxs-lookup"><span data-stu-id="f41ae-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="f41ae-106">Le classi derivate non possono richiamare direttamente gli eventi dichiarati all'interno della classe base.</span><span class="sxs-lookup"><span data-stu-id="f41ae-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="f41ae-107">Nonostante sia necessario a volte un evento che possa essere generato solo dalla classe base, nella maggior parte dei casi è opportuno consentire alla classe derivata di richiamare eventi della classe base.</span><span class="sxs-lookup"><span data-stu-id="f41ae-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="f41ae-108">A tale scopo, è possibile creare un metodo di chiamata protetto nella classe base che esegue il wrapping dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f41ae-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="f41ae-109">Le classi derivate possono richiamare indirettamente l'evento richiamando o eseguendo l'override di questo metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f41ae-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f41ae-110">Non dichiarare eventi virtuali in una classe base ed eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f41ae-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="f41ae-111">Il compilatore C# non è in grado di gestirli correttamente e non è possibile prevedere se un sottoscrittore dell'evento derivato sottoscriverà effettivamente l'evento della classe base.</span><span class="sxs-lookup"><span data-stu-id="f41ae-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f41ae-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f41ae-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f41ae-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f41ae-113">See also</span></span>

- [<span data-ttu-id="f41ae-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f41ae-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f41ae-115">Eventi</span><span class="sxs-lookup"><span data-stu-id="f41ae-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="f41ae-116">Delegati</span><span class="sxs-lookup"><span data-stu-id="f41ae-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="f41ae-117">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="f41ae-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="f41ae-118">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f41ae-118">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
