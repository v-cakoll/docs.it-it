---
title: Sicurezza di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 75016e9e04cf47782add18c87f7c677931743a4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556178"
---
# <a name="windows-forms-security"></a><span data-ttu-id="9126e-102">Sicurezza di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9126e-102">Windows Forms Security</span></span>
<span data-ttu-id="9126e-103">Form di Windows dispongono di un modello di sicurezza che è basata su codice (sicurezza livelli sono impostati per il codice, indipendentemente dall'utente che esegue il codice).</span><span class="sxs-lookup"><span data-stu-id="9126e-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="9126e-104">Si tratta di oltre agli eventuali schemi di sicurezza che potrebbero essere già presenti nel sistema informatico.</span><span class="sxs-lookup"><span data-stu-id="9126e-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="9126e-105">Tra cui gli schemi nel browser (ad esempio, la sicurezza basata sull'area disponibile in Internet Explorer) o il sistema operativo (ad esempio, la sicurezza basata su credenziali di Windows NT).</span><span class="sxs-lookup"><span data-stu-id="9126e-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9126e-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9126e-106">In This Section</span></span>  
 [<span data-ttu-id="9126e-107">Panoramica della sicurezza in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9126e-107">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 <span data-ttu-id="9126e-108">Viene illustrato brevemente il modello di sicurezza di .NET Framework e i passaggi di base necessari per assicurare che i form di Windows nell'applicazione siano protetti.</span><span class="sxs-lookup"><span data-stu-id="9126e-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="9126e-109">Accesso più sicuro a file e dati in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9126e-109">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="9126e-110">Viene descritto come accedere ai file e i dati in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="9126e-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="9126e-111">Stampa più sicura in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9126e-111">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="9126e-112">Viene descritto come accedere alle funzionalità di stampa in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="9126e-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="9126e-113">Considerazioni aggiuntive sulla sicurezza in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9126e-113">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="9126e-114">Descrive finestre, mediante gli Appunti ed eseguire chiamate a codice non gestito in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="9126e-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9126e-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9126e-115">Related Sections</span></span>  
 [<span data-ttu-id="9126e-116">NIB: Criteri di sicurezza predefiniti</span><span class="sxs-lookup"><span data-stu-id="9126e-116">NIB: Default Security Policy</span></span>](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 <span data-ttu-id="9126e-117">Elenca le autorizzazioni predefinite concesse nei set di autorizzazioni attendibilità completa, Intranet locale e Internet.</span><span class="sxs-lookup"><span data-stu-id="9126e-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 [<span data-ttu-id="9126e-118">NIB: Amministrazione di criteri di sicurezza generale</span><span class="sxs-lookup"><span data-stu-id="9126e-118">NIB: General Security Policy Administration</span></span>](https://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 <span data-ttu-id="9126e-119">Fornisce informazioni sull'amministrazione di criteri di sicurezza di .NET Framework e sull'elevazione delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9126e-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="9126e-120">Autorizzazioni pericolose e amministrazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="9126e-120">Dangerous Permissions and Policy Administration</span></span>](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="9126e-121">Vengono descritte alcune autorizzazioni di.NET Framework che possono potenzialmente consentire al sistema di sicurezza di essere aggirate.</span><span class="sxs-lookup"><span data-stu-id="9126e-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="9126e-122">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="9126e-122">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="9126e-123">Vengono forniti collegamenti ad argomenti che illustrano le procedure consigliate per la scrittura in modo sicuro di codice rispetto a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9126e-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 [<span data-ttu-id="9126e-124">NIB: Richiesta delle autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9126e-124">NIB: Requesting Permissions</span></span>](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 <span data-ttu-id="9126e-125">Viene illustrato l'utilizzo di attributi per informare il runtime di quali autorizzazioni deve eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="9126e-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="9126e-126">Concetti chiave sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="9126e-126">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="9126e-127">Collegamenti ad argomenti che trattano gli aspetti di base della sicurezza di codice.</span><span class="sxs-lookup"><span data-stu-id="9126e-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="9126e-128">Nozioni fondamentali sulla sicurezza per l’accesso al codice</span><span class="sxs-lookup"><span data-stu-id="9126e-128">Code Access Security Basics</span></span>](../../../docs/framework/misc/code-access-security-basics.md)  
 <span data-ttu-id="9126e-129">Vengono illustrate le nozioni fondamentali sull'utilizzo dei criteri di sicurezza del runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9126e-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 [<span data-ttu-id="9126e-130">NIB: Determinazione della necessità di modificare i criteri di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9126e-130">NIB: Determining When to Modify Security Policy</span></span>](https://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 <span data-ttu-id="9126e-131">Viene illustrato come determinare quando le applicazioni devono molto diversi da criteri di sicurezza predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9126e-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 [<span data-ttu-id="9126e-132">NIB: Distribuzione di criteri di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9126e-132">NIB: Deploying Security Policy</span></span>](https://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 <span data-ttu-id="9126e-133">Viene descritto il modo migliore per la distribuzione di modifiche ai criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9126e-133">Discusses the best manner for deploying security policy changes.</span></span>
