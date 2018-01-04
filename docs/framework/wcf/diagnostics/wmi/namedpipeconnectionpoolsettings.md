---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 601ccd5589da759606365570538e0df902e4fbe2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="8a4c7-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8a4c7-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="8a4c7-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8a4c7-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a4c7-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8a4c7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8a4c7-105">Methods</span></span>  
 <span data-ttu-id="8a4c7-106">La classe NamedPipeConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="8a4c7-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8a4c7-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8a4c7-107">Properties</span></span>  
 <span data-ttu-id="8a4c7-108">La classe NamedPipeConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a4c7-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="8a4c7-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="8a4c7-109">GroupName</span></span>  
 <span data-ttu-id="8a4c7-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="8a4c7-110">Data type: string</span></span>  
  
 <span data-ttu-id="8a4c7-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a4c7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a4c7-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="8a4c7-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="8a4c7-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="8a4c7-113">IdleTimeout</span></span>  
 <span data-ttu-id="8a4c7-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="8a4c7-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="8a4c7-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a4c7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a4c7-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="8a4c7-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="8a4c7-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8a4c7-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="8a4c7-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="8a4c7-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="8a4c7-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a4c7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a4c7-120">Numero massimo di connessioni in uscita per ogni endpoint sul client.</span><span class="sxs-lookup"><span data-stu-id="8a4c7-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a4c7-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a4c7-121">Requirements</span></span>  
  
|<span data-ttu-id="8a4c7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8a4c7-122">MOF</span></span>|<span data-ttu-id="8a4c7-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8a4c7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8a4c7-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8a4c7-124">Namespace</span></span>|<span data-ttu-id="8a4c7-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8a4c7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a4c7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a4c7-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
