---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485805"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="cc2fc-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cc2fc-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="cc2fc-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cc2fc-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc2fc-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cc2fc-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cc2fc-105">Methods</span></span>  
 <span data-ttu-id="cc2fc-106">La classe TcpTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="cc2fc-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cc2fc-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cc2fc-107">Properties</span></span>  
 <span data-ttu-id="cc2fc-108">La classe TcpTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc2fc-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="cc2fc-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="cc2fc-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="cc2fc-110">Tipo di dati: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="cc2fc-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="cc2fc-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cc2fc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc2fc-112">Impostazioni del pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="cc2fc-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="cc2fc-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="cc2fc-113">ListenBacklog</span></span>  
 <span data-ttu-id="cc2fc-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="cc2fc-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="cc2fc-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cc2fc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc2fc-116">Numero massimo di richieste di connessioni in coda che possono essere in sospeso.</span><span class="sxs-lookup"><span data-stu-id="cc2fc-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="cc2fc-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="cc2fc-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="cc2fc-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="cc2fc-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="cc2fc-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cc2fc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc2fc-120">Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione.</span><span class="sxs-lookup"><span data-stu-id="cc2fc-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="cc2fc-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="cc2fc-121">TeredoEnabled</span></span>  
 <span data-ttu-id="cc2fc-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="cc2fc-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="cc2fc-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cc2fc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cc2fc-124">Valore booleano che specifica se Teredo (una tecnologia per l'indirizzamento dei client dietro a firewall) è attivata.</span><span class="sxs-lookup"><span data-stu-id="cc2fc-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc2fc-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc2fc-125">Requirements</span></span>  
  
|<span data-ttu-id="cc2fc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="cc2fc-126">MOF</span></span>|<span data-ttu-id="cc2fc-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cc2fc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cc2fc-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cc2fc-128">Namespace</span></span>|<span data-ttu-id="cc2fc-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cc2fc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc2fc-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc2fc-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
