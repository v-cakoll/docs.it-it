---
title: Modifiche di rilievo della rete
description: Elenca le modifiche di rilievo apportate alle funzionalità di rete in .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 07e0b2e062ce244cd6312bbe08bcc63db4c74347
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859632"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="6cbcb-103">Modifiche di rilievo della rete</span><span class="sxs-lookup"><span data-stu-id="6cbcb-103">Networking breaking changes</span></span>

<span data-ttu-id="6cbcb-104">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbcb-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="6cbcb-105">Modifica</span><span class="sxs-lookup"><span data-stu-id="6cbcb-105">Breaking change</span></span> | <span data-ttu-id="6cbcb-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6cbcb-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="6cbcb-107">Il valore predefinito di HttpRequestMessage. Version è stato modificato in 1,1</span><span class="sxs-lookup"><span data-stu-id="6cbcb-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="6cbcb-108">3.0</span><span class="sxs-lookup"><span data-stu-id="6cbcb-108">3.0</span></span> |
| [<span data-ttu-id="6cbcb-109">WebClient. CancelAsync non viene sempre annullato immediatamente</span><span class="sxs-lookup"><span data-stu-id="6cbcb-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="6cbcb-110">2.0</span><span class="sxs-lookup"><span data-stu-id="6cbcb-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="6cbcb-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6cbcb-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="6cbcb-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cbcb-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
