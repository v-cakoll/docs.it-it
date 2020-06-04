---
title: "Procedura: Leggere le impostazioni dell'applicazione"
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 9b326341c54d652479776e3ab93a2b140f4531e0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410140"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="8e8ba-102">Procedura: leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e8ba-102">How to: Read Application Settings in Visual Basic</span></span>

<span data-ttu-id="8e8ba-103">È possibile leggere un'impostazione utente accedendo alla proprietà dell'impostazione nell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="8e8ba-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="8e8ba-104">L'oggetto `My.Settings` espone ogni impostazione come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e8ba-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="8e8ba-105">Il nome della proprietà corrisponde allo stesso nome dell'impostazione e il tipo di proprietà al tipo di impostazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ba-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="8e8ba-106">L'**ambito** dell'impostazione indica se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito **applicazione** è di sola lettura, mentre la proprietà di un'impostazione dell'ambito **utente** è di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="8e8ba-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="8e8ba-107">Per altre informazioni, vedere [Oggetto My.Settings](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="8e8ba-107">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e8ba-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e8ba-108">Example</span></span>  

 <span data-ttu-id="8e8ba-109">Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="8e8ba-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="8e8ba-110">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="8e8ba-110">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="8e8ba-111">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="8e8ba-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8ba-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e8ba-112">See also</span></span>

- [<span data-ttu-id="8e8ba-113">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="8e8ba-113">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="8e8ba-114">Procedura: modificare le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e8ba-114">How to: Change User Settings in Visual Basic</span></span>](how-to-change-user-settings.md)
- [<span data-ttu-id="8e8ba-115">Procedura: Mantenere le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e8ba-115">How to: Persist User Settings in Visual Basic</span></span>](how-to-persist-user-settings.md)
- [<span data-ttu-id="8e8ba-116">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e8ba-116">How to: Create Property Grids for User Settings in Visual Basic</span></span>](how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="8e8ba-117">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="8e8ba-117">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
