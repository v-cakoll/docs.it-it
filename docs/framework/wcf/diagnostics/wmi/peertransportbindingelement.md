---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 58bf07b0429ca2435b5aae3683ef69951a10003e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185183"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="0789d-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0789d-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="0789d-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0789d-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0789d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0789d-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0789d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0789d-105">Methods</span></span>  
 <span data-ttu-id="0789d-106">La classe PeerTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="0789d-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0789d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0789d-107">Properties</span></span>  
 <span data-ttu-id="0789d-108">La classe PeerTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0789d-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="0789d-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="0789d-109">ListenIPAddress</span></span>  
 <span data-ttu-id="0789d-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0789d-110">Data type: string</span></span>  
  
 <span data-ttu-id="0789d-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0789d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0789d-112">Indirizzo IP su cui il nodo del peer è in attesa di messaggi.</span><span class="sxs-lookup"><span data-stu-id="0789d-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="0789d-113">Porta</span><span class="sxs-lookup"><span data-stu-id="0789d-113">Port</span></span>  
 <span data-ttu-id="0789d-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="0789d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="0789d-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0789d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0789d-116">Porta di interfaccia di rete su cui l'associazione elabora messaggi del canale del peer.</span><span class="sxs-lookup"><span data-stu-id="0789d-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="0789d-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0789d-117">Security</span></span>  
 <span data-ttu-id="0789d-118">Tipo di dati: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="0789d-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="0789d-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0789d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0789d-120">Impostazioni di sicurezza del trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="0789d-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0789d-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0789d-121">Requirements</span></span>  
  
|<span data-ttu-id="0789d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="0789d-122">MOF</span></span>|<span data-ttu-id="0789d-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0789d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0789d-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="0789d-124">Namespace</span></span>|<span data-ttu-id="0789d-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0789d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0789d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0789d-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
