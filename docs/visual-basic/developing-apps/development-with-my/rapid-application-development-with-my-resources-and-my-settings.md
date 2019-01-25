---
title: Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4150d2f9634045351cb52e02c4f4807e55d118e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717902"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="7c826-102">Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c826-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="7c826-103">Il `My.Resources` oggetto consente di accedere alle risorse dell'applicazione e consente di recuperare in modo dinamico le risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c826-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="7c826-104">Recupero di risorse</span><span class="sxs-lookup"><span data-stu-id="7c826-104">Retrieving Resources</span></span>  
 <span data-ttu-id="7c826-105">Un numero di risorse, ad esempio i file audio, icone, immagini e stringhe può essere recuperato tramite il `My.Resources` oggetto.</span><span class="sxs-lookup"><span data-stu-id="7c826-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="7c826-106">Ad esempio, è possibile accedere i file di risorse specifiche delle impostazioni cultura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c826-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="7c826-107">Nell'esempio seguente imposta l'icona del form per l'icona denominato `Form1Icon` archiviati nel file di risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c826-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="7c826-108">Il `My.Resources` oggetto espone solo le risorse globali.</span><span class="sxs-lookup"><span data-stu-id="7c826-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="7c826-109">Non fornisce accesso ai file di risorse associati ai form.</span><span class="sxs-lookup"><span data-stu-id="7c826-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="7c826-110">È necessario accedere alle risorse form dal form.</span><span class="sxs-lookup"><span data-stu-id="7c826-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="7c826-111">Analogamente, il `My.Settings` oggetto consente di accedere alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="7c826-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="7c826-112">Per altre informazioni, vedere [oggetto My. Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) e [oggetto My. Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="7c826-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c826-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c826-113">See also</span></span>
- [<span data-ttu-id="7c826-114">Oggetto My.Resources</span><span class="sxs-lookup"><span data-stu-id="7c826-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="7c826-115">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="7c826-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="7c826-116">Accesso alle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7c826-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
