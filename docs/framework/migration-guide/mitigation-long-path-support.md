---
title: 'Mitigazione: Supporto del percorso lungo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 138e96c3d45b79ccf30f6a3d39f0af26a48c0117
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-long-path-support"></a><span data-ttu-id="38ba7-102">Mitigazione: Supporto del percorso lungo</span><span class="sxs-lookup"><span data-stu-id="38ba7-102">Mitigation: Long Path Support</span></span>
<span data-ttu-id="38ba7-103">A partire dalle applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], i metodi I/O del file system non generano più automaticamente un'eccezione <xref:System.IO.PathTooLongException> se un percorso o nome completo del file supera i 260 (o `MAX_PATH`) caratteri.</span><span class="sxs-lookup"><span data-stu-id="38ba7-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  file system I/O methods not longer automatically throw a <xref:System.IO.PathTooLongException> if a path or fully qualified file name exceeds 260 (or `MAX_PATH`) characters.</span></span> <span data-ttu-id="38ba7-104">Al contrario, sono supportati i percorsi lunghi con un massimo di 32 mila caratteri.</span><span class="sxs-lookup"><span data-stu-id="38ba7-104">Instead, long paths of up to 32K characters are supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="38ba7-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="38ba7-105">Impact</span></span>  
 <span data-ttu-id="38ba7-106">Le applicazioni ricompilate destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] e che in precedenza generavano automaticamente un'eccezione <xref:System.IO.PathTooLongException>, perché un percorso con più di 260 caratteri genera ora un'eccezione <xref:System.IO.PathTooLongException> solo nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38ba7-106">Apps recompiled to target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] and that previously threw a <xref:System.IO.PathTooLongException> automatically because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException> only under the following conditions:</span></span>  
  
-   <span data-ttu-id="38ba7-107">La lunghezza della stringa deve essere maggiore di <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) caratteri.</span><span class="sxs-lookup"><span data-stu-id="38ba7-107">The length of the path is greater than  <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) characters.</span></span>  
  
-   <span data-ttu-id="38ba7-108">Il sistema operativo restituisce `COR_E_PATHTOOLONG` o equivalente.</span><span class="sxs-lookup"><span data-stu-id="38ba7-108">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>  
  
 <span data-ttu-id="38ba7-109">Il comportamento legacy per le applicazioni destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti è che il runtime genera automaticamente un'eccezione <xref:System.IO.PathTooLongException> ogni volta che un percorso supera i 260 caratteri.</span><span class="sxs-lookup"><span data-stu-id="38ba7-109">The legacy behavior for apps that target the[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier is that the runtime automatically throws a <xref:System.IO.PathTooLongException> whenever a path exceeds 260 characters.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="38ba7-110">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="38ba7-110">Mitigation</span></span>  
 <span data-ttu-id="38ba7-111">Per le applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], è possibile rifiutare esplicitamente il supporto del percorso lungo, nel caso non sia opportuno, aggiungendo il codice seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione del file app. config:</span><span class="sxs-lookup"><span data-stu-id="38ba7-111">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can opt out of long path support if it is not desirable by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 <span data-ttu-id="38ba7-112">Per le applicazioni destinate alle versioni precedenti di .NET framework, ma eseguite in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive è possibile consentire esplicitamente il supporto per il percordo lungo aggiungendo il codice seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file app.config:</span><span class="sxs-lookup"><span data-stu-id="38ba7-112">For apps that target earlier versions of the .NET Framework but run on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later., you can opt in to long path support by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38ba7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38ba7-113">See Also</span></span>  
 [<span data-ttu-id="38ba7-114">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="38ba7-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

