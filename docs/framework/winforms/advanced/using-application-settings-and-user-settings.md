---
title: Utilizzo delle impostazioni applicazione e delle impostazioni utente
ms.date: 03/30/2017
description: Informazioni su come usare le impostazioni dell'applicazione e le impostazioni utente per creare e accedere ai valori resi permanente tra le sessioni di esecuzione dell'applicazione.
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: a30fd354986265eca002fce57bccf5b3bb2adc15
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903168"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="45b22-103">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="45b22-103">Using Application Settings and User Settings</span></span>
<span data-ttu-id="45b22-104">A partire da .NET Framework 2,0, è possibile creare e accedere ai valori resi permanente tra le sessioni di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45b22-104">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="45b22-105">Questi valori sono denominati *Impostazioni*.</span><span class="sxs-lookup"><span data-stu-id="45b22-105">These values are called *settings*.</span></span> <span data-ttu-id="45b22-106">Le impostazioni possono rappresentare le preferenze dell'utente o informazioni importanti che l'applicazione deve usare.</span><span class="sxs-lookup"><span data-stu-id="45b22-106">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="45b22-107">Ad esempio, è possibile creare una serie di impostazioni che archiviano le preferenze dell'utente per la combinazione di colori di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45b22-107">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="45b22-108">In alternativa, è possibile archiviare la stringa di connessione che specifica un database usato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45b22-108">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="45b22-109">Le impostazioni consentono sia di rendere permanente le informazioni cruciali per l'applicazione all'esterno del codice, sia di creare profili in cui archiviare le preferenze dei singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="45b22-109">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="45b22-110">Negli argomenti di questa sezione viene descritto come utilizzare le impostazioni in fase di progettazione e di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45b22-110">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45b22-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="45b22-111">In This Section</span></span>  
 [<span data-ttu-id="45b22-112">Procedura: creare una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="45b22-112">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="45b22-113">Viene illustrato come utilizzare Visual Studio per creare una nuova impostazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45b22-113">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="45b22-114">Procedura: modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="45b22-114">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="45b22-115">Viene descritto come usare Visual Studio per modificare il valore di un'impostazione esistente.</span><span class="sxs-lookup"><span data-stu-id="45b22-115">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="45b22-116">Procedura: modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="45b22-116">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="45b22-117">Viene illustrato in dettaglio come modificare il valore di un'impostazione in un'applicazione compilata tra sessioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45b22-117">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="45b22-118">Procedura: leggere le impostazioni in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="45b22-118">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="45b22-119">Viene descritto come usare il codice per leggere le impostazioni con C#.</span><span class="sxs-lookup"><span data-stu-id="45b22-119">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="45b22-120">Procedura: scrivere le impostazioni utente in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="45b22-120">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="45b22-121">Viene illustrato come usare il codice per scrivere e salvare i valori delle impostazioni utente con C#.</span><span class="sxs-lookup"><span data-stu-id="45b22-121">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="45b22-122">Procedura: aggiungere più set di impostazioni all'applicazione in C#</span><span class="sxs-lookup"><span data-stu-id="45b22-122">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="45b22-123">Informazioni dettagliate su come aggiungere più set di impostazioni a un'applicazione con C#.</span><span class="sxs-lookup"><span data-stu-id="45b22-123">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b22-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45b22-124">See also</span></span>

- [<span data-ttu-id="45b22-125">Impostazioni dell'applicazione per Windows Forms</span><span class="sxs-lookup"><span data-stu-id="45b22-125">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
