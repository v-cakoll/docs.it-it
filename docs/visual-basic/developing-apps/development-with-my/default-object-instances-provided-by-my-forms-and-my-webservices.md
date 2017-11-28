---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44265c3f6f38a001192a8d92f2fbb6edeaca21cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="5f3e1-102">Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f3e1-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="5f3e1-103">Il [Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) e [My. WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) oggetti forniscono accesso ai moduli, origini dati e servizi Web XML utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f3e1-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="5f3e1-104">A tal fine alle raccolte di *le istanze predefinite* di ognuno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="5f3e1-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="5f3e1-105">Istanze predefinite</span><span class="sxs-lookup"><span data-stu-id="5f3e1-105">Default Instances</span></span>  
 <span data-ttu-id="5f3e1-106">Un'istanza predefinita è un'istanza della classe che viene fornita dal runtime e non deve essere dichiarata e creata un'istanza utilizzando il `Dim` e `New` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5f3e1-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="5f3e1-107">Nell'esempio seguente viene illustrato come potrebbe avere dichiarato e creare un'istanza di un'istanza di un <xref:System.Windows.Forms.Form> classe denominata `Form1`, e come si sia in grado di ottenere un'istanza predefinita di questo <xref:System.Windows.Forms.Form> classe tramite `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="5f3e1-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 <span data-ttu-id="5f3e1-108">Il `My.Forms` oggetto restituisce una raccolta di istanze predefinite per ogni `Form` classe presente nel progetto.</span><span class="sxs-lookup"><span data-stu-id="5f3e1-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="5f3e1-109">Analogamente, `My.WebServices` fornisce un'istanza predefinita della classe proxy per ogni servizio Web che hanno creato un riferimento nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f3e1-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3e1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f3e1-110">See Also</span></span>  
 [<span data-ttu-id="5f3e1-111">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="5f3e1-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="5f3e1-112">Oggetto My.WebServices</span><span class="sxs-lookup"><span data-stu-id="5f3e1-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="5f3e1-113">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="5f3e1-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
