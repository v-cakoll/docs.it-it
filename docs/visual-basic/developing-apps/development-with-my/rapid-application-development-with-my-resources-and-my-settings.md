---
title: Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 808e02510d4f0a237ad4354b2edac8fa024b5f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582272"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="5ad68-102">Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ad68-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="5ad68-103">Il `My.Resources` oggetto fornisce l'accesso alle risorse dell'applicazione e consente di recuperare in modo dinamico le risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ad68-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="5ad68-104">Recupero di risorse</span><span class="sxs-lookup"><span data-stu-id="5ad68-104">Retrieving Resources</span></span>  
 <span data-ttu-id="5ad68-105">Un numero di risorse, ad esempio file audio, icone, immagini e stringhe può essere recuperato tramite il `My.Resources` oggetto.</span><span class="sxs-lookup"><span data-stu-id="5ad68-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="5ad68-106">Ad esempio, è possibile accedere il file di risorse specifiche delle impostazioni cultura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ad68-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="5ad68-107">Nell'esempio seguente imposta l'icona del form per l'icona denominato `Form1Icon` archiviati nel file di risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ad68-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="5ad68-108">Il `My.Resources` oggetto espone solo le risorse globali.</span><span class="sxs-lookup"><span data-stu-id="5ad68-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="5ad68-109">Non fornisce accesso ai file di risorse associato al form.</span><span class="sxs-lookup"><span data-stu-id="5ad68-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="5ad68-110">È necessario accedere alle risorse di modulo dal modulo.</span><span class="sxs-lookup"><span data-stu-id="5ad68-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="5ad68-111">Analogamente, il `My.Settings` oggetto fornisce accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="5ad68-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="5ad68-112">Per ulteriori informazioni, vedere [oggetto My. Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) e [oggetto My. Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="5ad68-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad68-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ad68-113">See Also</span></span>  
 [<span data-ttu-id="5ad68-114">Oggetto My.Resources</span><span class="sxs-lookup"><span data-stu-id="5ad68-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="5ad68-115">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="5ad68-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="5ad68-116">Accesso alle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5ad68-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
