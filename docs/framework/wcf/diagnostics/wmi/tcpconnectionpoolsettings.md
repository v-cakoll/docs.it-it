---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 6fa68eed241edaea40b66c31240a4201e05779f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975348"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="737ae-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="737ae-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="737ae-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="737ae-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="737ae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="737ae-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="737ae-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="737ae-105">Methods</span></span>  
 <span data-ttu-id="737ae-106">La classe TcpConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="737ae-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="737ae-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="737ae-107">Properties</span></span>  
 <span data-ttu-id="737ae-108">La classe TcpConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="737ae-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="737ae-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="737ae-109">GroupName</span></span>  
 <span data-ttu-id="737ae-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="737ae-110">Data type: string</span></span>  
  
 <span data-ttu-id="737ae-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="737ae-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="737ae-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="737ae-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="737ae-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="737ae-113">IdleTimeout</span></span>  
 <span data-ttu-id="737ae-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="737ae-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="737ae-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="737ae-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="737ae-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="737ae-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="737ae-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="737ae-117">LeaseTimeout</span></span>  
 <span data-ttu-id="737ae-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="737ae-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="737ae-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="737ae-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="737ae-120">Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="737ae-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="737ae-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="737ae-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="737ae-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="737ae-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="737ae-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="737ae-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="737ae-124">Numero massimo di connessioni in uscita per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="737ae-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="737ae-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="737ae-125">Requirements</span></span>  
  
|<span data-ttu-id="737ae-126">MOF</span><span class="sxs-lookup"><span data-stu-id="737ae-126">MOF</span></span>|<span data-ttu-id="737ae-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="737ae-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="737ae-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="737ae-128">Namespace</span></span>|<span data-ttu-id="737ae-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="737ae-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="737ae-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="737ae-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
