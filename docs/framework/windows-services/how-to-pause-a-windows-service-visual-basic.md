---
title: 'Procedura: Sospendere un servizio Windows (Visual Basic)'
description: Informazioni su come usare il componente ServiceController per sospendere un servizio Windows, ad esempio il servizio di amministrazione di IIS, in un computer locale con Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 628cc2e896f7f8a289e52674b721c4aef605854c
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925566"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="6a887-103">Procedura: Sospendere un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a887-103">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="6a887-104">Questo esempio usa il componente <xref:System.ServiceProcess.ServiceController> per sospendere l'esecuzione del servizio IIS Admin nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="6a887-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a887-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a887-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="6a887-106">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="6a887-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="6a887-107">Nello strumento di selezione dei frammenti di codice il frammento si trova in **Sistema operativo Windows > Servizi Windows**.</span><span class="sxs-lookup"><span data-stu-id="6a887-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="6a887-108">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="6a887-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a887-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6a887-109">Compiling the Code</span></span>  
 <span data-ttu-id="6a887-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a887-110">This example requires:</span></span>  
  
- <span data-ttu-id="6a887-111">Un riferimento del progetto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="6a887-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="6a887-112">Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="6a887-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="6a887-113">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="6a887-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="6a887-114">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="6a887-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6a887-115">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="6a887-115">Robust Programming</span></span>  
 <span data-ttu-id="6a887-116">La proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> della classe <xref:System.ServiceProcess.ServiceController> è il computer locale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6a887-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="6a887-117">Per fare riferimento a servizi di Windows in un altro computer, modificare la proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> impostando il nome di tale computer.</span><span class="sxs-lookup"><span data-stu-id="6a887-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="6a887-118">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="6a887-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="6a887-119">Il servizio non può essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="6a887-119">The service cannot be paused.</span></span> <span data-ttu-id="6a887-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="6a887-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="6a887-121">Si è verificato un errore durante l'accesso a un'API di sistema.</span><span class="sxs-lookup"><span data-stu-id="6a887-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="6a887-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="6a887-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6a887-123">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a887-123">.NET Framework Security</span></span>  
 <span data-ttu-id="6a887-124">Il controllo dei servizi nel computer può essere limitato usando <xref:System.ServiceProcess.ServiceControllerPermissionAccess> per impostare le autorizzazioni in <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="6a887-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="6a887-125">L'accesso alle informazioni sul servizio può essere limitato tramite <xref:System.Security.Permissions.PermissionState> per impostare le autorizzazioni in <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="6a887-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a887-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a887-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="6a887-127">Procedura: Continuare un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a887-127">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
