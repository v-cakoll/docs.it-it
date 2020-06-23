---
title: 'Procedura: scrivere le impostazioni utente in fase di esecuzione con C#'
description: Informazioni su come scrivere le impostazioni in fase di esecuzione con C# salvando in modo permanente le modifiche apportate alle impostazioni tra sessioni dell'applicazione chiamando il metodo Save.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904325"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="750b8-103">Procedura: scrivere le impostazioni utente in fase di esecuzione con C\#</span><span class="sxs-lookup"><span data-stu-id="750b8-103">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="750b8-104">Le impostazioni con ambito di applicazione sono di sola lettura e possono essere modificate solo in fase di progettazione o modificando il file .config tra sessioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="750b8-104">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="750b8-105">Le impostazioni con ambito di utente possono invece essere scritte in fase di esecuzione usando la stessa procedura adottata per modificare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="750b8-105">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="750b8-106">Il nuovo valore viene mantenuto per la durata della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="750b8-106">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="750b8-107">È possibile mantenere le modifiche alle impostazioni tra le sessioni dell'applicazione chiamando il metodo Save.</span><span class="sxs-lookup"><span data-stu-id="750b8-107">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="750b8-108">Procedura: scrivere e salvare in modo permanente le impostazioni utente in fase di esecuzione con C\#</span><span class="sxs-lookup"><span data-stu-id="750b8-108">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="750b8-109">Accedere all'impostazione e assegnarle un nuovo valore come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="750b8-109">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="750b8-110">Se si vogliono mantenere le modifiche alle impostazioni tra sessioni dell'applicazione, chiamare il metodo Save, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="750b8-110">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="750b8-111">Le impostazioni utente vengono salvate in un file all'interno di una sottocartella della cartella dati applicazioni nascosta locale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="750b8-111">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750b8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="750b8-112">See also</span></span>

- [<span data-ttu-id="750b8-113">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="750b8-113">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="750b8-114">Procedura: leggere le impostazioni in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="750b8-114">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="750b8-115">Panoramica delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="750b8-115">Application Settings Overview</span></span>](application-settings-overview.md)
