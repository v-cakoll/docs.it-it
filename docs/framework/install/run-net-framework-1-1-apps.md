---
title: Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10
ms.custom: 
ms.date: 05/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d5b99390e62984b37b0d7267c40b1221f556f60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="3b8cd-102">Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b8cd-102">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="3b8cd-103">.NET Framework 1.1 non è supportato nei sistemi operativi [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-103">The .NET Framework 1.1 is not supported on the [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or the Windows 10 operating systems.</span></span> <span data-ttu-id="3b8cd-104">In alcuni casi, .NET Framework 1.1 viene identificato specificamente come obbligatorio per l'esecuzione di un'app.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-104">In some cases, the .NET Framework 1.1 is specifically identified as required for an app to run.</span></span> <span data-ttu-id="3b8cd-105">In questi casi è necessario contattare il fornitore di software indipendente (ISV), per aggiornare l'app e poterla eseguire in [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-105">In those cases, you should contact your independent software vendor (ISV) to have the app upgraded to run on the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] or later version.</span></span> <span data-ttu-id="3b8cd-106">Per altre informazioni, vedere [Migrazione da .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="3b8cd-106">For additional information, see [Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="3b8cd-107">Installare .NET Framework 1.1 da un CD o dall'Area download</span><span class="sxs-lookup"><span data-stu-id="3b8cd-107">Install the .NET Framework 1.1 from a CD or Download Center</span></span>

<span data-ttu-id="3b8cd-108">Non è possibile installare manualmente .NET Framework 1.1 in [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-108">It isn't possible to manually install the .NET Framework 1.1 on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or Windows 10.</span></span> <span data-ttu-id="3b8cd-109">e non è più supportato.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-109">It is no longer supported.</span></span> <span data-ttu-id="3b8cd-110">Se si tenta di installare il pacchetto, viene visualizzato il seguente messaggio di errore: "Impossibile continuare. La versione corrente di .NET Framework è incompatibile con una versione precedentemente installata".</span><span class="sxs-lookup"><span data-stu-id="3b8cd-110">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="3b8cd-111">Per risolvere questo problema, installare [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22).</span><span class="sxs-lookup"><span data-stu-id="3b8cd-111">To solve this problem, install the [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="3b8cd-112">Questa versione include .NET Framework 2.0 (la versione successiva a .NET Framework 1.1), che è supportata da [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-112">This version includes the .NET Framework 2.0 (the release that follows the .NET Framework 1.1), which is supported on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], and Windows 10.</span></span> <span data-ttu-id="3b8cd-113">È consigliabile iniziare sempre installando l'app per determinare se viene aggiornata automaticamente a una versione successiva di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-113">You should always try to install the app first to determine if it will automatically be updated to a later version of the .NET Framework.</span></span> <span data-ttu-id="3b8cd-114">In caso contrario, contattare il fornitore di software indipendente (ISV) per un aggiornamento dell'app.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-114">If it does not, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b8cd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b8cd-115">See also</span></span>

<span data-ttu-id="3b8cd-116">[Migrazione da .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span><span class="sxs-lookup"><span data-stu-id="3b8cd-116">[Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span></span>
