---
title: "Procedura: Modificare le impostazioni dell'utente"
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: d24b6d239c894788ce67b0723b4bf034050bf307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74329621"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="14a1c-102">Procedura: modificare le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14a1c-102">How to: Change User Settings in Visual Basic</span></span>

<span data-ttu-id="14a1c-103">È possibile modificare un'impostazione utente assegnando un nuovo valore alla proprietà dell'impostazione nell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="14a1c-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="14a1c-104">L'oggetto `My.Settings` espone ogni impostazione come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="14a1c-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="14a1c-105">Il nome della proprietà corrisponde allo stesso nome dell'impostazione e il tipo di proprietà al tipo di impostazione.</span><span class="sxs-lookup"><span data-stu-id="14a1c-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="14a1c-106">L'**ambito** dell'impostazione determina se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito dell'**applicazione** è di sola lettura, mentre la proprietà di un'impostazione dell'ambito dell'**utente**-è di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="14a1c-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="14a1c-107">Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="14a1c-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14a1c-108">Sebbene sia possibile modificare e salvare i valori delle impostazioni dell'ambito dell'utente in fase di esecuzione, le impostazioni dell'ambito dell'applicazione sono di sola lettura e non possono essere modificate a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="14a1c-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="14a1c-109">È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14a1c-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="14a1c-110">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="14a1c-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14a1c-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="14a1c-111">Example</span></span>  

 <span data-ttu-id="14a1c-112">Questo esempio modifica il valore dell'impostazione utente `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="14a1c-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 <span data-ttu-id="14a1c-113">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione utente `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="14a1c-113">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="14a1c-114">Alla chiusura dell'applicazione vengono salvate le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="14a1c-114">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="14a1c-115">Per salvare immediatamente le impostazioni, chiamare il metodo `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="14a1c-115">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="14a1c-116">Per altre informazioni, vedere [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="14a1c-116">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a1c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14a1c-117">See also</span></span>

- [<span data-ttu-id="14a1c-118">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="14a1c-118">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="14a1c-119">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14a1c-119">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="14a1c-120">Procedura: Mantenere le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14a1c-120">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="14a1c-121">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14a1c-121">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="14a1c-122">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="14a1c-122">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
