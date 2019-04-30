---
title: 'Procedura: Leggere le impostazioni in fase di esecuzione con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966915"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="c05ec-102">Procedura: Leggere le impostazioni in fase di esecuzione con C\#</span><span class="sxs-lookup"><span data-stu-id="c05ec-102">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="c05ec-103">È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà.</span><span class="sxs-lookup"><span data-stu-id="c05ec-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="c05ec-104">L'oggetto Proprietà espone tutte le impostazioni predefinite per il progetto tramite il membro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="c05ec-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="c05ec-105">Leggere le impostazioni in fase di esecuzione con C\#</span><span class="sxs-lookup"><span data-stu-id="c05ec-105">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="c05ec-106">Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="c05ec-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="c05ec-107">Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor.</span><span class="sxs-lookup"><span data-stu-id="c05ec-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="c05ec-108">È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="c05ec-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="c05ec-109">Per informazioni sulla creazione di un file di impostazioni, vedere [How To: Creare una nuova impostazione in fase di progettazione](how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="c05ec-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c05ec-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c05ec-110">See also</span></span>

- [<span data-ttu-id="c05ec-111">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="c05ec-111">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="c05ec-112">Procedura: Scrivere le impostazioni utente in fase di esecuzione conC#</span><span class="sxs-lookup"><span data-stu-id="c05ec-112">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="c05ec-113">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="c05ec-113">Application Settings Overview</span></span>](application-settings-overview.md)
