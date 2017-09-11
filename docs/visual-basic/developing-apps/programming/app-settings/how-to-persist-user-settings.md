---
title: 'Procedura: mantenere le impostazioni dell''utente in Visual Basic'
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
- My.Settings object, persisting user settings
- persistence, persisting user settings [Visual Basic]
- user settings, persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
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
ms.openlocfilehash: a5553acd031db7e9be9c87afaeba61aea9bb2111
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="7c263-102">Procedura: mantenere le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7c263-102">How to: Persist User Settings in Visual Basic</span></span>
<span data-ttu-id="7c263-103">È possibile usare il metodo `My.Settings.Save` per mantenere le modifiche apportate alle impostazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c263-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="7c263-104">In genere, le applicazioni sono progettate per rendere permanenti le modifiche alle impostazioni dell'utente quando l'applicazione si arresta.</span><span class="sxs-lookup"><span data-stu-id="7c263-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="7c263-105">Questo avviene perché il salvataggio delle impostazioni può richiedere diversi secondi, in base a una serie di fattori.</span><span class="sxs-lookup"><span data-stu-id="7c263-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="7c263-106">Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="7c263-106">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c263-107">Mentre è possibile modificare e salvare i valori delle impostazioni dell'ambito dell'utente in fase di esecuzione, le impostazioni dell'ambito dell'applicazione sono di sola lettura e non possono essere modificate a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7c263-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="7c263-108">È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c263-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="7c263-109">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7c263-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c263-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c263-110">Example</span></span>  
 <span data-ttu-id="7c263-111">In questo esempio viene modificato il valore dell'impostazione utente `LastChanged` e la modifica viene salvata chiamando il metodo `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="7c263-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 <span data-ttu-id="7c263-112">[!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c263-112">[!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]</span></span>  
  
 <span data-ttu-id="7c263-113">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione utente `LastChanged` di tipo `Date`.</span><span class="sxs-lookup"><span data-stu-id="7c263-113">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="7c263-114">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7c263-114">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c263-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c263-115">See Also</span></span>  
 <span data-ttu-id="7c263-116">[Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="7c263-116">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="7c263-117">[Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7c263-117">[How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
 <span data-ttu-id="7c263-118">[Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7c263-118">[How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
 <span data-ttu-id="7c263-119">[Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7c263-119">[How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
 [<span data-ttu-id="7c263-120">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="7c263-120">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

