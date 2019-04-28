---
title: Utilizzo delle impostazioni applicazione e delle impostazioni utente
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: ea6994e653b3a06239634f5a0fddea84a07086e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777182"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="9d1c7-102">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="9d1c7-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="9d1c7-103">A partire da .NET Framework 2.0, è possibile creare e accedere ai valori che vengono rese persistenti tra le sessioni di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="9d1c7-104">Questi valori sono denominati *impostazioni*.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-104">These values are called *settings*.</span></span> <span data-ttu-id="9d1c7-105">Le impostazioni possono rappresentare le preferenze dell'utente, o informazioni importanti dell'applicazione devono usare.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="9d1c7-106">Ad esempio, si potrebbe creare una serie di impostazioni che memorizzano le preferenze utente per la combinazione di colori di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="9d1c7-107">Oppure è possibile archiviare la stringa di connessione che specifica un database che usa l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="9d1c7-108">Le impostazioni consentono di mantenere le informazioni essenziali per l'applicazione all'esterno del codice e creare i profili che archiviano le preferenze dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="9d1c7-109">Gli argomenti in questa sezione descrivono come usare le impostazioni in fase di progettazione e tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d1c7-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9d1c7-110">In This Section</span></span>  
 [<span data-ttu-id="9d1c7-111">Procedura: Creare una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="9d1c7-111">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="9d1c7-112">Viene illustrato come usare Visual Studio per creare una nuova impostazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="9d1c7-113">Procedura: Modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="9d1c7-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="9d1c7-114">Viene descritto come usare Visual Studio per modificare il valore di un'impostazione esistente.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="9d1c7-115">Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="9d1c7-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="9d1c7-116">Illustra come modificare il valore di un'impostazione in un'applicazione compilata tra sessioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="9d1c7-117">Procedura: Leggere le impostazioni in fase di esecuzione conC#</span><span class="sxs-lookup"><span data-stu-id="9d1c7-117">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="9d1c7-118">Viene descritto come usare il codice per leggere le impostazioni con C#.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="9d1c7-119">Procedura: Scrivere le impostazioni utente in fase di esecuzione conC#</span><span class="sxs-lookup"><span data-stu-id="9d1c7-119">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="9d1c7-120">Viene illustrato come usare il codice per scrivere e salvare i valori delle impostazioni utente con C#.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="9d1c7-121">Procedura: Aggiungere all'applicazione in più set di impostazioniC#</span><span class="sxs-lookup"><span data-stu-id="9d1c7-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="9d1c7-122">Spiega come aggiungere più set di impostazioni a un'applicazione con C#.</span><span class="sxs-lookup"><span data-stu-id="9d1c7-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d1c7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d1c7-123">See also</span></span>

- [<span data-ttu-id="9d1c7-124">Impostazioni delle applicazioni per Windows Form</span><span class="sxs-lookup"><span data-stu-id="9d1c7-124">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
