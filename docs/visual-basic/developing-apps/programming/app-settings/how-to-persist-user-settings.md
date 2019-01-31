---
title: 'Procedura: Salvare in modo permanente le impostazioni utente in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: dab285f175838fb71e4218cbafdd4f7593c9e786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611293"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="d19a6-102">Procedura: Salvare in modo permanente le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d19a6-102">How to: Persist User Settings in Visual Basic</span></span>
<span data-ttu-id="d19a6-103">È possibile usare il metodo `My.Settings.Save` per mantenere le modifiche apportate alle impostazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d19a6-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="d19a6-104">In genere, le applicazioni sono progettate per rendere permanenti le modifiche alle impostazioni dell'utente quando l'applicazione si arresta.</span><span class="sxs-lookup"><span data-stu-id="d19a6-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="d19a6-105">Questo avviene perché il salvataggio delle impostazioni può richiedere diversi secondi, in base a una serie di fattori.</span><span class="sxs-lookup"><span data-stu-id="d19a6-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="d19a6-106">Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="d19a6-106">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d19a6-107">Mentre è possibile modificare e salvare i valori delle impostazioni dell'ambito dell'utente in fase di esecuzione, le impostazioni dell'ambito dell'applicazione sono di sola lettura e non possono essere modificate a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d19a6-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="d19a6-108">È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d19a6-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="d19a6-109">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d19a6-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d19a6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d19a6-110">Example</span></span>  
 <span data-ttu-id="d19a6-111">In questo esempio viene modificato il valore dell'impostazione utente `LastChanged` e la modifica viene salvata chiamando il metodo `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="d19a6-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 <span data-ttu-id="d19a6-112">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione utente `LastChanged` di tipo `Date`.</span><span class="sxs-lookup"><span data-stu-id="d19a6-112">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="d19a6-113">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d19a6-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19a6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d19a6-114">See also</span></span>
- [<span data-ttu-id="d19a6-115">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="d19a6-115">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="d19a6-116">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d19a6-116">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="d19a6-117">Procedura: Modificare le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d19a6-117">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="d19a6-118">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d19a6-118">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="d19a6-119">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="d19a6-119">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
