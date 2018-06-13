---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 68e6a25e4e3f47c556363e2fd5aa8d3bb9946449
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485645"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="3aa95-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3aa95-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="3aa95-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3aa95-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aa95-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3aa95-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3aa95-105">Methods</span></span>  
 <span data-ttu-id="3aa95-106">La classe PeerTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3aa95-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3aa95-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3aa95-107">Properties</span></span>  
 <span data-ttu-id="3aa95-108">La classe PeerTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa95-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="3aa95-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="3aa95-109">ListenIPAddress</span></span>  
 <span data-ttu-id="3aa95-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3aa95-110">Data type: string</span></span>  
  
 <span data-ttu-id="3aa95-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa95-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa95-112">Indirizzo IP su cui il nodo del peer è in attesa di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3aa95-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="3aa95-113">Porta</span><span class="sxs-lookup"><span data-stu-id="3aa95-113">Port</span></span>  
 <span data-ttu-id="3aa95-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3aa95-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3aa95-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa95-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa95-116">Porta di interfaccia di rete su cui l'associazione elabora messaggi del canale del peer.</span><span class="sxs-lookup"><span data-stu-id="3aa95-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="3aa95-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3aa95-117">Security</span></span>  
 <span data-ttu-id="3aa95-118">Tipo di dati: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="3aa95-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="3aa95-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3aa95-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3aa95-120">Impostazioni di sicurezza del trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="3aa95-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa95-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aa95-121">Requirements</span></span>  
  
|<span data-ttu-id="3aa95-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3aa95-122">MOF</span></span>|<span data-ttu-id="3aa95-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3aa95-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3aa95-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3aa95-124">Namespace</span></span>|<span data-ttu-id="3aa95-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3aa95-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3aa95-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aa95-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
