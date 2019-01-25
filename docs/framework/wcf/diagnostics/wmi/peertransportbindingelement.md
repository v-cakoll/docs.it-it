---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 437ccc0446e3cc05596ab12b7908177b7f78e431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670654"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="8994a-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="8994a-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="8994a-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="8994a-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8994a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8994a-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8994a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8994a-105">Methods</span></span>  
 <span data-ttu-id="8994a-106">La classe PeerTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="8994a-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8994a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8994a-107">Properties</span></span>  
 <span data-ttu-id="8994a-108">La classe PeerTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="8994a-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="8994a-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="8994a-109">ListenIPAddress</span></span>  
 <span data-ttu-id="8994a-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="8994a-110">Data type: string</span></span>  
  
 <span data-ttu-id="8994a-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8994a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8994a-112">Indirizzo IP su cui il nodo del peer è in attesa di messaggi.</span><span class="sxs-lookup"><span data-stu-id="8994a-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="8994a-113">Porta</span><span class="sxs-lookup"><span data-stu-id="8994a-113">Port</span></span>  
 <span data-ttu-id="8994a-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="8994a-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="8994a-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8994a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8994a-116">Porta di interfaccia di rete su cui l'associazione elabora messaggi del canale del peer.</span><span class="sxs-lookup"><span data-stu-id="8994a-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="8994a-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8994a-117">Security</span></span>  
 <span data-ttu-id="8994a-118">Tipo di dati: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="8994a-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="8994a-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8994a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8994a-120">Impostazioni di sicurezza del trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="8994a-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8994a-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8994a-121">Requirements</span></span>  
  
|<span data-ttu-id="8994a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8994a-122">MOF</span></span>|<span data-ttu-id="8994a-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8994a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8994a-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8994a-124">Namespace</span></span>|<span data-ttu-id="8994a-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8994a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8994a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8994a-126">See also</span></span>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
