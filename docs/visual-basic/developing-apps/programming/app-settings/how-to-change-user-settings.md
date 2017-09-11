---
title: 'Procedura: modificare le impostazioni dell''utente in Visual Basic'
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
- user settings, changing in Visual Basic
- user settings
- My.Settings object, changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
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
ms.openlocfilehash: bfc5e5959d691e6a5f77fcffdb61c99bafa29aac
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="eb70a-102">Procedura: modificare le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eb70a-102">How to: Change User Settings in Visual Basic</span></span>
<span data-ttu-id="eb70a-103">È possibile modificare un'impostazione utente assegnando un nuovo valore alla proprietà dell'impostazione nell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="eb70a-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="eb70a-104">L'oggetto `My.Settings` espone ogni impostazione come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb70a-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="eb70a-105">Il nome della proprietà corrisponde allo stesso nome dell'impostazione e il tipo di proprietà al tipo di impostazione.</span><span class="sxs-lookup"><span data-stu-id="eb70a-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="eb70a-106">L'**ambito** dell'impostazione determina se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito dell'**applicazione** è di sola lettura, mentre la proprietà di un'impostazione dell'ambito dell'**utente**-è di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="eb70a-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="eb70a-107">Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="eb70a-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb70a-108">Sebbene sia possibile modificare e salvare i valori delle impostazioni dell'ambito dell'utente in fase di esecuzione, le impostazioni dell'ambito dell'applicazione sono di sola lettura e non possono essere modificate a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="eb70a-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="eb70a-109">È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb70a-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="eb70a-110">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="eb70a-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb70a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb70a-111">Example</span></span>  
 <span data-ttu-id="eb70a-112">Questo esempio modifica il valore dell'impostazione utente `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="eb70a-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 <span data-ttu-id="eb70a-113">[!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb70a-113">[!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]</span></span>  
  
 <span data-ttu-id="eb70a-114">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione utente `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="eb70a-114">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="eb70a-115">Alla chiusura dell'applicazione vengono salvate le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="eb70a-115">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="eb70a-116">Per salvare immediatamente le impostazioni, chiamare il metodo `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="eb70a-116">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="eb70a-117">Per altre informazioni, vedere [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="eb70a-117">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb70a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb70a-118">See Also</span></span>  
 <span data-ttu-id="eb70a-119">[Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="eb70a-119">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="eb70a-120">[Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="eb70a-120">[How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
 <span data-ttu-id="eb70a-121">[Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="eb70a-121">[How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
 <span data-ttu-id="eb70a-122">[Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="eb70a-122">[How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
 [<span data-ttu-id="eb70a-123">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="eb70a-123">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

