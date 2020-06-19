---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 141f2f5f98499498d3c6732f7ae8d0abe6259ed9
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990250"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="551c5-102">Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="551c5-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="551c5-103">Gli oggetti [My. Forms](../../language-reference/objects/my-forms-object.md) e [My. WebServices](../../language-reference/objects/my-webservices-object.md) consentono di accedere ai moduli, alle origini dati e ai servizi Web XML utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="551c5-103">The [My.Forms](../../language-reference/objects/my-forms-object.md) and [My.WebServices](../../language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="551c5-104">Forniscono l'accesso tramite raccolte di *istanze predefinite* di ognuno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="551c5-104">They provide access through collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="551c5-105">Istanze predefinite</span><span class="sxs-lookup"><span data-stu-id="551c5-105">Default Instances</span></span>  

 <span data-ttu-id="551c5-106">Un'istanza predefinita è un'istanza della classe fornita dal runtime e non è necessario dichiararla e crearne un'istanza usando le `Dim` `New` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="551c5-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="551c5-107">Nell'esempio seguente viene illustrato come dichiarare e creare un'istanza di una <xref:System.Windows.Forms.Form> classe denominata e `Form1` come ora è possibile ottenere un'istanza predefinita di questa <xref:System.Windows.Forms.Form> classe tramite `My.Forms` .</span><span class="sxs-lookup"><span data-stu-id="551c5-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="551c5-108">L' `My.Forms` oggetto restituisce una raccolta di istanze predefinite per ogni `Form` classe esistente nel progetto.</span><span class="sxs-lookup"><span data-stu-id="551c5-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="551c5-109">Analogamente, `My.WebServices` fornisce un'istanza predefinita della classe proxy per ogni servizio Web a cui è stato creato un riferimento nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="551c5-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551c5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="551c5-110">See also</span></span>

- [<span data-ttu-id="551c5-111">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="551c5-111">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="551c5-112">Oggetto My.WebServices</span><span class="sxs-lookup"><span data-stu-id="551c5-112">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="551c5-113">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="551c5-113">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
