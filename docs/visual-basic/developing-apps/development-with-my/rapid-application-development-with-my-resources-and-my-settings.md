---
title: Sviluppo rapido di applicazioni con My.Resources e My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: fd1ec25582e919b84235502f5921edfbc6e1dade
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990207"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="0e258-102">Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e258-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>

<span data-ttu-id="0e258-103">L' `My.Resources` oggetto fornisce l'accesso alle risorse dell'applicazione e consente di recuperare in modo dinamico le risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e258-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="0e258-104">Recupero di risorse</span><span class="sxs-lookup"><span data-stu-id="0e258-104">Retrieving Resources</span></span>  

 <span data-ttu-id="0e258-105">Tramite l'oggetto è possibile recuperare diverse risorse, ad esempio file audio, icone, immagini e stringhe `My.Resources` .</span><span class="sxs-lookup"><span data-stu-id="0e258-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="0e258-106">Ad esempio, è possibile accedere ai file di risorse specifici delle impostazioni cultura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e258-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="0e258-107">Nell'esempio seguente viene impostata l'icona del form sull'icona denominata `Form1Icon` archiviato nel file di risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e258-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="0e258-108">L' `My.Resources` oggetto espone solo le risorse globali.</span><span class="sxs-lookup"><span data-stu-id="0e258-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="0e258-109">Non fornisce l'accesso ai file di risorse associati ai moduli.</span><span class="sxs-lookup"><span data-stu-id="0e258-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="0e258-110">Accedere alle risorse del modulo dal form.</span><span class="sxs-lookup"><span data-stu-id="0e258-110">Access the form resources from the form.</span></span>  
  
 <span data-ttu-id="0e258-111">Analogamente, l' `My.Settings` oggetto fornisce l'accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare dinamicamente le impostazioni delle proprietà e altre informazioni per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e258-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="0e258-112">Per altre informazioni, vedere oggetto [My. resources](../../language-reference/objects/my-resources-object.md) e [My. Settings](../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="0e258-112">For more information, see [My.Resources Object](../../language-reference/objects/my-resources-object.md) and [My.Settings Object](../../language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e258-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e258-113">See also</span></span>

- [<span data-ttu-id="0e258-114">Oggetto My.Resources</span><span class="sxs-lookup"><span data-stu-id="0e258-114">My.Resources Object</span></span>](../../language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="0e258-115">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="0e258-115">My.Settings Object</span></span>](../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="0e258-116">Accessing Application Settings</span><span class="sxs-lookup"><span data-stu-id="0e258-116">Accessing Application Settings</span></span>](../programming/app-settings/index.md)
