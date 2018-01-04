---
title: TcpConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04e6a457a9f4c3f93a52f851aafe70578b7d7444
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="f4d0c-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f4d0c-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="f4d0c-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f4d0c-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4d0c-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f4d0c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f4d0c-105">Methods</span></span>  
 <span data-ttu-id="f4d0c-106">La classe TcpConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="f4d0c-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f4d0c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f4d0c-107">Properties</span></span>  
 <span data-ttu-id="f4d0c-108">La classe TcpConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4d0c-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="f4d0c-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="f4d0c-109">GroupName</span></span>  
 <span data-ttu-id="f4d0c-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="f4d0c-110">Data type: string</span></span>  
  
 <span data-ttu-id="f4d0c-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f4d0c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f4d0c-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="f4d0c-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="f4d0c-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f4d0c-113">IdleTimeout</span></span>  
 <span data-ttu-id="f4d0c-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="f4d0c-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="f4d0c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f4d0c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f4d0c-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="f4d0c-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="f4d0c-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="f4d0c-117">LeaseTimeout</span></span>  
 <span data-ttu-id="f4d0c-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="f4d0c-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="f4d0c-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f4d0c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f4d0c-120">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="f4d0c-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="f4d0c-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f4d0c-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="f4d0c-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="f4d0c-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="f4d0c-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f4d0c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f4d0c-124">Numero massimo di connessioni in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="f4d0c-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d0c-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4d0c-125">Requirements</span></span>  
  
|<span data-ttu-id="f4d0c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="f4d0c-126">MOF</span></span>|<span data-ttu-id="f4d0c-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f4d0c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f4d0c-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f4d0c-128">Namespace</span></span>|<span data-ttu-id="f4d0c-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f4d0c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4d0c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4d0c-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
