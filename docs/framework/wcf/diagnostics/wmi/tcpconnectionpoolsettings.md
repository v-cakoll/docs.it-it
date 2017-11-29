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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5038d093333eca9ca191c3ecae4cfa889d723276
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="e715c-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e715c-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="e715c-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e715c-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e715c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e715c-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e715c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e715c-105">Methods</span></span>  
 <span data-ttu-id="e715c-106">La classe TcpConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="e715c-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e715c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e715c-107">Properties</span></span>  
 <span data-ttu-id="e715c-108">La classe TcpConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="e715c-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="e715c-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="e715c-109">GroupName</span></span>  
 <span data-ttu-id="e715c-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="e715c-110">Data type: string</span></span>  
  
 <span data-ttu-id="e715c-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e715c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e715c-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="e715c-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="e715c-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="e715c-113">IdleTimeout</span></span>  
 <span data-ttu-id="e715c-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e715c-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e715c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e715c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e715c-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="e715c-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="e715c-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="e715c-117">LeaseTimeout</span></span>  
 <span data-ttu-id="e715c-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e715c-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="e715c-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e715c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e715c-120">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="e715c-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="e715c-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e715c-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="e715c-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e715c-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="e715c-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="e715c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e715c-124">Numero massimo di connessioni in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="e715c-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e715c-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e715c-125">Requirements</span></span>  
  
|<span data-ttu-id="e715c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e715c-126">MOF</span></span>|<span data-ttu-id="e715c-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e715c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e715c-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e715c-128">Namespace</span></span>|<span data-ttu-id="e715c-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e715c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e715c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e715c-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
