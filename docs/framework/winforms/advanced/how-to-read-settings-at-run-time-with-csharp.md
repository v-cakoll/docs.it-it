---
title: 'Procedura: leggere le impostazioni in fase di esecuzione con C#'
description: Informazioni su come leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione con C# tramite l'oggetto Properties.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903352"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="13532-103">Procedura: leggere le impostazioni in fase di esecuzione con C\#</span><span class="sxs-lookup"><span data-stu-id="13532-103">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="13532-104">È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà.</span><span class="sxs-lookup"><span data-stu-id="13532-104">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="13532-105">L'oggetto Properties espone tutte le impostazioni predefinite per il progetto tramite il membro Properties. Settings. default nello spazio dei nomi predefinito del progetto in cui sono definiti.</span><span class="sxs-lookup"><span data-stu-id="13532-105">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member in the default namespace of the project they are defined in.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="13532-106">Per leggere le impostazioni in fase di esecuzione con C\#</span><span class="sxs-lookup"><span data-stu-id="13532-106">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="13532-107">Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="13532-107">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="13532-108">Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor.</span><span class="sxs-lookup"><span data-stu-id="13532-108">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="13532-109">È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="13532-109">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="13532-110">Per informazioni sulla creazione di un file di impostazioni, vedere [procedura: creare una nuova impostazione in fase di progettazione](how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="13532-110">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="13532-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13532-111">See also</span></span>

- [<span data-ttu-id="13532-112">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="13532-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="13532-113">Procedura: scrivere le impostazioni utente in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="13532-113">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="13532-114">Panoramica delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="13532-114">Application Settings Overview</span></span>](application-settings-overview.md)
