---
title: Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ddaf9965a3b3b5d6171a643b198db93309afad48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="50d3a-102">Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="50d3a-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="50d3a-103">Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="50d3a-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="50d3a-104">che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori.</span><span class="sxs-lookup"><span data-stu-id="50d3a-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="50d3a-105">L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag di <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="50d3a-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="50d3a-106">Gli assembly gestiti non dispongono di autorizzazioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="50d3a-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="50d3a-107">Per le applicazioni in esecuzione nell'area attendibile (computer locale) e nell'area Intranet, viene concessa l'autorizzazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="50d3a-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="50d3a-108">Le applicazioni in esecuzione nell'area Internet non è assolutamente consentite di eseguire il reindirizzamento dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="50d3a-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="50d3a-109">L'autorizzazione non è necessaria se il reindirizzamento di assembly viene eseguito in un file dei criteri editore controllato dall'editore del componente o nel file di configurazione del computer che viene controllato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="50d3a-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="50d3a-110">Tuttavia, l'autorizzazione è necessaria per un'applicazione ignorare in modo esplicito criteri editore utilizzando il [ \<publisherPolicy applicare = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="50d3a-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="50d3a-111">La tabella seguente mostra il valore predefinito di impostazioni di sicurezza per il **BindingRedirects** flag.</span><span class="sxs-lookup"><span data-stu-id="50d3a-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="50d3a-112">Zona</span><span class="sxs-lookup"><span data-stu-id="50d3a-112">Zone</span></span>|<span data-ttu-id="50d3a-113">Impostazione del flag BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="50d3a-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="50d3a-114">Area siti attendibili (computer locale)</span><span class="sxs-lookup"><span data-stu-id="50d3a-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="50d3a-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="50d3a-115">**ON**</span></span>|  
|<span data-ttu-id="50d3a-116">L'area Intranet</span><span class="sxs-lookup"><span data-stu-id="50d3a-116">Intranet Zone</span></span>|<span data-ttu-id="50d3a-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="50d3a-117">**ON**</span></span>|  
|<span data-ttu-id="50d3a-118">Area Internet</span><span class="sxs-lookup"><span data-stu-id="50d3a-118">Internet Zone</span></span>|<span data-ttu-id="50d3a-119">**DISATTIVATO**</span><span class="sxs-lookup"><span data-stu-id="50d3a-119">**OFF**</span></span>|  
|<span data-ttu-id="50d3a-120">Zone non attendibili</span><span class="sxs-lookup"><span data-stu-id="50d3a-120">Untrusted zones</span></span>|<span data-ttu-id="50d3a-121">**DISATTIVATO**</span><span class="sxs-lookup"><span data-stu-id="50d3a-121">**OFF**</span></span>|  
  
 <span data-ttu-id="50d3a-122">Un amministratore può modificare queste impostazioni di sicurezza per il supporto o limitare per scenari specifici su un determinato computer.</span><span class="sxs-lookup"><span data-stu-id="50d3a-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="50d3a-123">Non sono disponibili strumenti per la modifica di **BindingRedirects** impostazione del flag dall'impostazione predefinita; un amministratore deve modificare manualmente il file Security. config sul computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="50d3a-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d3a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50d3a-124">See Also</span></span>  
 [<span data-ttu-id="50d3a-125">File dei criteri editore e l'esecuzione Side-by-Side</span><span class="sxs-lookup"><span data-stu-id="50d3a-125">Publisher Policy Files and Side-by-Side Execution</span></span>](http://msdn.microsoft.com/en-us/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="50d3a-126">Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="50d3a-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="50d3a-127">Esecuzione side-by-Side</span><span class="sxs-lookup"><span data-stu-id="50d3a-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
