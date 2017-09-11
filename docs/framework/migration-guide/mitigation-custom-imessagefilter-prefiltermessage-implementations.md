---
title: 'Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: b37d1d7ff75aebfcdf3e849931a5d2b3924d5d7a
ms.openlocfilehash: fe7290f3a887f2c4d52e52a6aff708e0e9fe415f
ms.contentlocale: it-it
ms.lasthandoff: 09/06/2017

---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="c6da9-102">Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate</span><span class="sxs-lookup"><span data-stu-id="c6da9-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>
<span data-ttu-id="c6da9-103">Nelle app di Windows Form destinate a versioni di .NET Framework a partire da [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], un'implementazione <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> personalizzata può filtrare in modo sicuro i messaggi quando il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> viene chiamato se l'implementazione <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:</span><span class="sxs-lookup"><span data-stu-id="c6da9-103">In Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> implementation:</span></span>  
  
-   <span data-ttu-id="c6da9-104">Esegue una o entrambe le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6da9-104">Does one or both of the following:</span></span>  
  
    -   <span data-ttu-id="c6da9-105">Aggiunge un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6da9-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>  
  
    -   <span data-ttu-id="c6da9-106">Rimuove un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6da9-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="c6da9-107">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="c6da9-107">method.</span></span>  
  
-   <span data-ttu-id="c6da9-108">**E** immette i messaggi chiamando il metodo <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c6da9-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="c6da9-109">Impatto</span><span class="sxs-lookup"><span data-stu-id="c6da9-109">Impact</span></span>  
 <span data-ttu-id="c6da9-110">Questa modifica riguarda solo app Windows Form destinate a versioni di .NET Framework che iniziano con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6da9-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="c6da9-111">Per le app Windows Form destinate a versioni precedenti di .NET Framework, questo tipo di implementazioni in alcuni casi genera un'eccezione <xref:System.IndexOutOfRangeException> quando viene chiamato il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c6da9-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> method is called</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="c6da9-112">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="c6da9-112">Mitigation</span></span>  
 <span data-ttu-id="c6da9-113">Se la modifica è indesiderata, le app destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva la possono rifiutare esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="c6da9-113">If this change is undesirable, apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 <span data-ttu-id="c6da9-114">Le app destinate a versioni precedenti di .NET Framework ma in esecuzione su [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva possono optare per questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="c6da9-114">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6da9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6da9-115">See Also</span></span>  
 [<span data-ttu-id="c6da9-116">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="c6da9-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

