---
title: Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b9b9ac5c4e8ce08b9f926b0cdf7149dbdd9ac2da
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501433"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="70c04-102">Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="70c04-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="70c04-103">Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="70c04-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="70c04-104">che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori.</span><span class="sxs-lookup"><span data-stu-id="70c04-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="70c04-105">L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag nella <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="70c04-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="70c04-106">Gli assembly gestiti non dispongono di autorizzazioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="70c04-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="70c04-107">Viene concessa l'autorizzazione di sicurezza alle applicazioni in esecuzione nell'area attendibile (computer locale) e nell'area Intranet.</span><span class="sxs-lookup"><span data-stu-id="70c04-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="70c04-108">Le applicazioni in esecuzione nell'area Internet sono assolutamente consentite di eseguire il reindirizzamento di associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="70c04-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="70c04-109">L'autorizzazione non è obbligatorio se viene eseguito il reindirizzamento di assembly in un file di criteri di autore che è controllato dall'editore del componente, o nel file di configurazione del computer che viene controllato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="70c04-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="70c04-110">Tuttavia, l'autorizzazione è necessaria per un'applicazione ignorare in modo esplicito server di pubblicazione dei criteri tramite il [ \<publisherPolicy applicare = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70c04-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="70c04-111">La tabella seguente mostra il valore predefinito delle impostazioni di sicurezza per il **BindingRedirects** flag.</span><span class="sxs-lookup"><span data-stu-id="70c04-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="70c04-112">Zona</span><span class="sxs-lookup"><span data-stu-id="70c04-112">Zone</span></span>|<span data-ttu-id="70c04-113">Impostazione del flag BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="70c04-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="70c04-114">Area attendibile (computer locale)</span><span class="sxs-lookup"><span data-stu-id="70c04-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="70c04-115">**VIA**</span><span class="sxs-lookup"><span data-stu-id="70c04-115">**ON**</span></span>|  
|<span data-ttu-id="70c04-116">Area Intranet</span><span class="sxs-lookup"><span data-stu-id="70c04-116">Intranet Zone</span></span>|<span data-ttu-id="70c04-117">**VIA**</span><span class="sxs-lookup"><span data-stu-id="70c04-117">**ON**</span></span>|  
|<span data-ttu-id="70c04-118">Area Internet</span><span class="sxs-lookup"><span data-stu-id="70c04-118">Internet Zone</span></span>|<span data-ttu-id="70c04-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="70c04-119">**OFF**</span></span>|  
|<span data-ttu-id="70c04-120">Zone non attendibili</span><span class="sxs-lookup"><span data-stu-id="70c04-120">Untrusted zones</span></span>|<span data-ttu-id="70c04-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="70c04-121">**OFF**</span></span>|  
  
 <span data-ttu-id="70c04-122">Un amministratore può modificare queste impostazioni di sicurezza per il supporto o limitare gli scenari specifici in un determinato computer.</span><span class="sxs-lookup"><span data-stu-id="70c04-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="70c04-123">Non sono disponibili strumenti per la modifica di **BindingRedirects** flag impostazione dal valore predefinito; un amministratore deve modificare manualmente il file Security. config nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="70c04-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c04-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70c04-124">See Also</span></span>  
 [<span data-ttu-id="70c04-125">File dei criteri editore ed esecuzione Side-by-Side</span><span class="sxs-lookup"><span data-stu-id="70c04-125">Publisher Policy Files and Side-by-Side Execution</span></span>](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="70c04-126">Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="70c04-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="70c04-127">Esecuzione side-by-side</span><span class="sxs-lookup"><span data-stu-id="70c04-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
