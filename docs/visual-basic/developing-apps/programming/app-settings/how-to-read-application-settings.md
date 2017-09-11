---
title: 'Procedura: leggere le impostazioni dell''applicazione in Visual Basic'
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
- reading application settings
- My.Settings object, reading application settings
- application settings, reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e18c1da475ac7945a8bf080aad3ba2905d5d8658
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="30f07-102">Procedura: leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30f07-102">How to: Read Application Settings in Visual Basic</span></span>
<span data-ttu-id="30f07-103">È possibile leggere un'impostazione utente accedendo alla proprietà dell'impostazione nell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="30f07-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="30f07-104">L'oggetto `My.Settings` espone ogni impostazione come proprietà.</span><span class="sxs-lookup"><span data-stu-id="30f07-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="30f07-105">Il nome della proprietà corrisponde al nome dell'impostazione e il tipo di proprietà al tipo di impostazione.</span><span class="sxs-lookup"><span data-stu-id="30f07-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="30f07-106">L'**ambito** dell'impostazione indica se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito **applicazione** è di sola lettura, mentre la proprietà di un'impostazione dell'ambito **utente** è di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="30f07-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="30f07-107">Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="30f07-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30f07-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="30f07-108">Example</span></span>  
 <span data-ttu-id="30f07-109">Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="30f07-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="30f07-110">[!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="30f07-110">[!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]</span></span>  
  
 <span data-ttu-id="30f07-111">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="30f07-111">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="30f07-112">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="30f07-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f07-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30f07-113">See Also</span></span>  
 <span data-ttu-id="30f07-114">[Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="30f07-114">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="30f07-115">[Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="30f07-115">[How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
 <span data-ttu-id="30f07-116">[Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="30f07-116">[How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
 <span data-ttu-id="30f07-117">[Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="30f07-117">[How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
 [<span data-ttu-id="30f07-118">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="30f07-118">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

