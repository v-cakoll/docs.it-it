---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 4a30ad3ddfef5d39942345b0e0d5274eeff8e596
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485922"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="e8bb0-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e8bb0-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="e8bb0-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e8bb0-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8bb0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8bb0-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e8bb0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e8bb0-105">Methods</span></span>  
 <span data-ttu-id="e8bb0-106">La classe TcpConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="e8bb0-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e8bb0-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e8bb0-107">Properties</span></span>  
 <span data-ttu-id="e8bb0-108">La classe TcpConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8bb0-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="e8bb0-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="e8bb0-109">GroupName</span></span>  
 <span data-ttu-id="e8bb0-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="e8bb0-110">Data type: string</span></span>  
  
 <span data-ttu-id="e8bb0-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8bb0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8bb0-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="e8bb0-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="e8bb0-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="e8bb0-113">IdleTimeout</span></span>  
 <span data-ttu-id="e8bb0-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e8bb0-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e8bb0-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8bb0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8bb0-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="e8bb0-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="e8bb0-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="e8bb0-117">LeaseTimeout</span></span>  
 <span data-ttu-id="e8bb0-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e8bb0-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="e8bb0-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8bb0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8bb0-120">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="e8bb0-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="e8bb0-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e8bb0-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="e8bb0-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e8bb0-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="e8bb0-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8bb0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8bb0-124">Numero massimo di connessioni in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="e8bb0-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8bb0-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8bb0-125">Requirements</span></span>  
  
|<span data-ttu-id="e8bb0-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e8bb0-126">MOF</span></span>|<span data-ttu-id="e8bb0-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e8bb0-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e8bb0-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e8bb0-128">Namespace</span></span>|<span data-ttu-id="e8bb0-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e8bb0-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8bb0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8bb0-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
