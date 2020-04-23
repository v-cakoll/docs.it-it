---
title: 'Procedura: continuare un servizio Windows (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: a10e05b0460608a9e67ee4527adf80be3d47438e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053630"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="78359-102">Procedura: continuare un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78359-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="78359-103">Questo esempio usa il componente <xref:System.ServiceProcess.ServiceController> per continuare l'esecuzione del servizio IIS Admin nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="78359-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78359-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="78359-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="78359-105">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="78359-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="78359-106">Nello strumento di selezione dei frammenti di codice il frammento si trova in **Sistema operativo Windows > Servizi Windows**.</span><span class="sxs-lookup"><span data-stu-id="78359-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="78359-107">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="78359-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="78359-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="78359-108">Compiling the Code</span></span>  
 <span data-ttu-id="78359-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="78359-109">This example requires:</span></span>  
  
- <span data-ttu-id="78359-110">Un riferimento del progetto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="78359-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="78359-111">Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="78359-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="78359-112">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="78359-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="78359-113">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="78359-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="78359-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="78359-114">Robust Programming</span></span>  
 <span data-ttu-id="78359-115">La proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> della classe <xref:System.ServiceProcess.ServiceController> è il computer locale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="78359-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="78359-116">Per fare riferimento a servizi di Windows in un altro computer, modificare la proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> impostando il nome di tale computer.</span><span class="sxs-lookup"><span data-stu-id="78359-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="78359-117">Non è possibile chiamare il metodo <xref:System.ServiceProcess.ServiceController.Continue%2A> su un servizio fino a quando lo stato del controller del servizio è <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="78359-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="78359-118">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="78359-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="78359-119">Non è possibile riprendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="78359-119">The service cannot be resumed.</span></span> <span data-ttu-id="78359-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="78359-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="78359-121">Si è verificato un errore durante l'accesso a un'API di sistema.</span><span class="sxs-lookup"><span data-stu-id="78359-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="78359-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="78359-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="78359-123">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78359-123">.NET Framework Security</span></span>  
 <span data-ttu-id="78359-124">Il controllo dei servizi nel computer può essere limitato tramite l'enumerazione <xref:System.ServiceProcess.ServiceControllerPermissionAccess> per impostare le autorizzazioni nella classe <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="78359-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="78359-125">L'accesso alle informazioni sul servizio può essere limitato tramite l'enumerazione <xref:System.Security.Permissions.PermissionState> per impostare le autorizzazioni nella classe <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="78359-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78359-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78359-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="78359-127">Procedura: sospendere un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78359-127">How to: Pause a Windows Service (Visual Basic)</span></span>](how-to-pause-a-windows-service-visual-basic.md)
