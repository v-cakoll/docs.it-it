---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 5a81cde63de258f0996c3ddbc99e0102d58d79b8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973912"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="26c88-102">Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26c88-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="26c88-103">Il [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) e [My. WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) oggetti forniscono l'accesso a form, origini dati e servizi Web XML usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26c88-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="26c88-104">Ciò avviene grazie alle raccolte di *le istanze predefinite* della ognuno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="26c88-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="26c88-105">Istanze predefinite</span><span class="sxs-lookup"><span data-stu-id="26c88-105">Default Instances</span></span>  
 <span data-ttu-id="26c88-106">Un'istanza predefinita è un'istanza della classe che viene fornita dal runtime e non deve essere dichiarato e creare un'istanza usando il `Dim` e `New` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="26c88-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="26c88-107">Nell'esempio seguente viene illustrato come si dispone di dichiarare e creare un'istanza di un'istanza di un <xref:System.Windows.Forms.Form> classe denominata `Form1`, e come sono ora in grado di ottenere un'istanza predefinita di questo <xref:System.Windows.Forms.Form> classe tramite `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="26c88-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="26c88-108">Il `My.Forms` object restituisce una raccolta di istanze predefinite di ogni `Form` classe esistente nel progetto.</span><span class="sxs-lookup"><span data-stu-id="26c88-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="26c88-109">Analogamente, `My.WebServices` fornisce un'istanza predefinita della classe proxy per tutti i servizi Web che hanno creato un riferimento a nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26c88-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c88-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26c88-110">See also</span></span>
- [<span data-ttu-id="26c88-111">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="26c88-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="26c88-112">Oggetto My.WebServices</span><span class="sxs-lookup"><span data-stu-id="26c88-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="26c88-113">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="26c88-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
