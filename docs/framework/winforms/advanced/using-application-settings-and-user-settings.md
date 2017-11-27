---
title: Utilizzo delle impostazioni applicazione e delle impostazioni utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9544b6af74608bd1b29db3250e887999ae3187f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="1851e-102">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="1851e-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="1851e-103">A partire da .NET Framework 2.0, è possibile creare e accedere ai valori che sono persistenti tra le sessioni di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1851e-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="1851e-104">Questi valori sono denominati *impostazioni*.</span><span class="sxs-lookup"><span data-stu-id="1851e-104">These values are called *settings*.</span></span> <span data-ttu-id="1851e-105">Le impostazioni possono rappresentare le preferenze dell'utente o informazioni importanti, l'applicazione devono utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1851e-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="1851e-106">Ad esempio, è possibile creare una serie di impostazioni per archiviare le preferenze utente per la combinazione di colori di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1851e-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="1851e-107">Oppure è possibile archiviare la stringa di connessione che specifica un database che utilizza l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1851e-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="1851e-108">Impostazioni consentono di mantenere le informazioni essenziali per l'applicazione all'esterno del codice e creare i profili che archiviano le preferenze di singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="1851e-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="1851e-109">Negli argomenti di questa sezione viene descritto come utilizzare le impostazioni in fase di progettazione e di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1851e-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1851e-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1851e-110">In This Section</span></span>  
 [<span data-ttu-id="1851e-111">Procedura: Creare una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1851e-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="1851e-112">Viene illustrato come utilizzare Visual Studio per creare una nuova impostazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1851e-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="1851e-113">Procedura: Modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1851e-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="1851e-114">Viene descritto come utilizzare Visual Studio per modificare il valore di un'impostazione esistente.</span><span class="sxs-lookup"><span data-stu-id="1851e-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="1851e-115">Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="1851e-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="1851e-116">Viene illustrato come modificare il valore di un'impostazione di un'applicazione compilata tra le sessioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1851e-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="1851e-117">Procedura: Leggere le impostazioni in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="1851e-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="1851e-118">Viene descritto come usare il codice per leggere le impostazioni con c#.</span><span class="sxs-lookup"><span data-stu-id="1851e-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="1851e-119">Procedura: Scrivere le impostazioni utente in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="1851e-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="1851e-120">Viene illustrato come utilizzare codice per scrivere e salvare i valori delle impostazioni utente con c#.</span><span class="sxs-lookup"><span data-stu-id="1851e-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="1851e-121">Procedura: Aggiungere più set di impostazioni all'applicazione in C#</span><span class="sxs-lookup"><span data-stu-id="1851e-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="1851e-122">Viene illustrato come aggiungere più set di impostazioni per un'applicazione con c#.</span><span class="sxs-lookup"><span data-stu-id="1851e-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1851e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1851e-123">See Also</span></span>  
 [<span data-ttu-id="1851e-124">Impostazioni delle applicazioni per Windows Form</span><span class="sxs-lookup"><span data-stu-id="1851e-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)
