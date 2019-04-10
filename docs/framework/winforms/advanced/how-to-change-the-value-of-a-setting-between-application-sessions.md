---
title: "Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318897"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="4ad72-102">Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4ad72-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="4ad72-103">In alcuni casi, si potrebbe voler modificare il valore di un'impostazione tra le sessioni dell'applicazione dopo aver compilata e distribuita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ad72-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="4ad72-104">Ad esempio, si potrebbe voler modificare una stringa di connessione in modo che punti al percorso database corretto.</span><span class="sxs-lookup"><span data-stu-id="4ad72-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="4ad72-105">Poiché gli strumenti di progettazione non sono disponibili dopo aver compilata e distribuita l'applicazione, è necessario modificare il valore dell'impostazione manualmente nel file.</span><span class="sxs-lookup"><span data-stu-id="4ad72-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="4ad72-106">Per modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4ad72-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1. <span data-ttu-id="4ad72-107">Usa Microsoft Notepad o alcuni altri editor di testo o XML, aprire il file config associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ad72-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2. <span data-ttu-id="4ad72-108">Individuare la voce per l'impostazione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="4ad72-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="4ad72-109">Dovrebbe essere simile all'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4ad72-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. <span data-ttu-id="4ad72-110">Digitare un nuovo valore per l'impostazione e salvare il file.</span><span class="sxs-lookup"><span data-stu-id="4ad72-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad72-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad72-111">See also</span></span>

- [<span data-ttu-id="4ad72-112">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="4ad72-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="4ad72-113">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="4ad72-113">Application Settings Overview</span></span>](application-settings-overview.md)
