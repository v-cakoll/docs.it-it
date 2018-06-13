---
title: 'Procedura: scrivere le impostazioni utente in fase di esecuzione con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: f289b6a6a4a726ffa6bb2c9df99c665e2872e8d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522295"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="bf171-102">Procedura: scrivere le impostazioni utente in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="bf171-102">How To: Write User Settings at Run Time with C#</span></span> #
<span data-ttu-id="bf171-103">Le impostazioni con ambito di applicazione sono di sola lettura e possono essere modificate solo in fase di progettazione o modificando il file .config tra sessioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf171-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="bf171-104">Le impostazioni con ambito di utente possono invece essere scritte in fase di esecuzione usando la stessa procedura adottata per modificare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="bf171-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="bf171-105">Il nuovo valore viene mantenuto per la durata della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf171-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="bf171-106">È possibile mantenere le modifiche alle impostazioni tra le sessioni dell'applicazione chiamando il metodo Save.</span><span class="sxs-lookup"><span data-stu-id="bf171-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="bf171-107">Procedura: Scrivere e mantenere le impostazioni utente in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="bf171-107">How To: Write and Persist User Settings at Run Time with C#</span></span>  
  
1.  <span data-ttu-id="bf171-108">Accedere all'impostazione e assegnarle un nuovo valore come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bf171-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  <span data-ttu-id="bf171-109">Se si vogliono mantenere le modifiche alle impostazioni tra sessioni dell'applicazione, chiamare il metodo Save, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bf171-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     <span data-ttu-id="bf171-110">Le impostazioni utente vengono salvate in un file all'interno di una sottocartella della cartella dati applicazioni nascosta locale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bf171-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf171-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf171-111">See Also</span></span>  
 [<span data-ttu-id="bf171-112">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="bf171-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="bf171-113">Procedura: Leggere le impostazioni in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="bf171-113">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="bf171-114">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="bf171-114">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
