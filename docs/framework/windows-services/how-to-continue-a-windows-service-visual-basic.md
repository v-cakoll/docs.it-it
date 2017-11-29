---
title: 'Procedura: continuare un servizio Windows (Visual Basic)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 28dbbf2376416a340ad7853c026b2f763f695dcb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="7ff72-102">Procedura: continuare un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff72-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="7ff72-103">Questo esempio viene utilizzato il <xref:System.ServiceProcess.ServiceController> componente di riprendere il servizio di amministrazione di IIS nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7ff72-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ff72-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ff72-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="7ff72-105">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7ff72-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="7ff72-106">In selezione frammento di codice, si trova in **sistema operativo Windows > Windows Services**.</span><span class="sxs-lookup"><span data-stu-id="7ff72-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="7ff72-107">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="7ff72-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ff72-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7ff72-108">Compiling the Code</span></span>  
 <span data-ttu-id="7ff72-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ff72-109">This example requires:</span></span>  
  
-   <span data-ttu-id="7ff72-110">Un riferimento progetto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="7ff72-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="7ff72-111">Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="7ff72-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="7ff72-112">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="7ff72-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="7ff72-113">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="7ff72-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7ff72-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7ff72-114">Robust Programming</span></span>  
 <span data-ttu-id="7ff72-115">Il <xref:System.ServiceProcess.ServiceController.MachineName%2A> proprietà la <xref:System.ServiceProcess.ServiceController> classe è il computer locale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7ff72-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="7ff72-116">Per fare riferimento a servizi di Windows in un altro computer, modificare il <xref:System.ServiceProcess.ServiceController.MachineName%2A> proprietà sul nome del computer.</span><span class="sxs-lookup"><span data-stu-id="7ff72-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="7ff72-117">Non è possibile chiamare il <xref:System.ServiceProcess.ServiceController.Continue%2A> metodo su un servizio fino a quando lo stato del servizio controller è <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="7ff72-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="7ff72-118">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="7ff72-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7ff72-119">Impossibile riprendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="7ff72-119">The service cannot be resumed.</span></span> <span data-ttu-id="7ff72-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="7ff72-120">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="7ff72-121">Si è verificato un errore durante l'accesso a un'API di sistema.</span><span class="sxs-lookup"><span data-stu-id="7ff72-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="7ff72-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="7ff72-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7ff72-123">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7ff72-123">.NET Framework Security</span></span>  
 <span data-ttu-id="7ff72-124">Il controllo dei servizi del computer può essere limitato tramite la <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumerazione come impostare le autorizzazioni di <xref:System.ServiceProcess.ServiceControllerPermission> classe.</span><span class="sxs-lookup"><span data-stu-id="7ff72-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="7ff72-125">Utilizzando, è possibile limitare l'accesso alle informazioni sul servizio di <xref:System.Security.Permissions.PermissionState> enumerazione come impostare le autorizzazioni di <xref:System.Security.Permissions.SecurityPermission> classe.</span><span class="sxs-lookup"><span data-stu-id="7ff72-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff72-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ff72-126">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [<span data-ttu-id="7ff72-127">Procedura: sospendere un servizio di Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff72-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
