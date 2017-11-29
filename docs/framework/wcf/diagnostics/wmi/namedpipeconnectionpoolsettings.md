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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf9c39334289cb30d1a01917c0be37da02fcdc5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="c0fe6-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c0fe6-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="c0fe6-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c0fe6-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0fe6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0fe6-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c0fe6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c0fe6-105">Methods</span></span>  
 <span data-ttu-id="c0fe6-106">La classe NamedPipeConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c0fe6-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c0fe6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c0fe6-107">Properties</span></span>  
 <span data-ttu-id="c0fe6-108">La classe NamedPipeConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0fe6-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="c0fe6-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="c0fe6-109">GroupName</span></span>  
 <span data-ttu-id="c0fe6-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c0fe6-110">Data type: string</span></span>  
  
 <span data-ttu-id="c0fe6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0fe6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0fe6-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="c0fe6-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="c0fe6-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="c0fe6-113">IdleTimeout</span></span>  
 <span data-ttu-id="c0fe6-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="c0fe6-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="c0fe6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0fe6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0fe6-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="c0fe6-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="c0fe6-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c0fe6-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="c0fe6-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c0fe6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0fe6-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c0fe6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0fe6-120">Numero massimo di connessioni in uscita per ogni endpoint sul client.</span><span class="sxs-lookup"><span data-stu-id="c0fe6-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0fe6-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0fe6-121">Requirements</span></span>  
  
|<span data-ttu-id="c0fe6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c0fe6-122">MOF</span></span>|<span data-ttu-id="c0fe6-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c0fe6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c0fe6-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c0fe6-124">Namespace</span></span>|<span data-ttu-id="c0fe6-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c0fe6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0fe6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0fe6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
