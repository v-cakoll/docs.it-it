---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: 5c68706c5dcec3a5b0ec62bb9cfbea4e1496b4f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574599"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="a65fc-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a65fc-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="a65fc-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a65fc-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a65fc-104">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a65fc-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a65fc-105">Methods</span></span>  
 <span data-ttu-id="a65fc-106">La classe LocalServiceSecuritySettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a65fc-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a65fc-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a65fc-107">Properties</span></span>  
 <span data-ttu-id="a65fc-108">La classe LocalServiceSecuritySettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a65fc-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="a65fc-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="a65fc-109">DetectReplays</span></span>  
 <span data-ttu-id="a65fc-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="a65fc-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="a65fc-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-112">Valore booleano che specifica se gli attacchi di tipo replay contro il canale vengono rilevati e gestiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a65fc-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="a65fc-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="a65fc-113">InactivityTimeout</span></span>  
 <span data-ttu-id="a65fc-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-116">Numero massimo di sessioni di sicurezza in sospeso supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="a65fc-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="a65fc-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="a65fc-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="a65fc-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-120">TimeSpan che specifica la durata per tutti i nuovi cookie di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a65fc-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="a65fc-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="a65fc-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="a65fc-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="a65fc-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="a65fc-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-124">Numero massimo di cookie che possono essere memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="a65fc-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="a65fc-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="a65fc-125">MaxClockSkew</span></span>  
 <span data-ttu-id="a65fc-126">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-128">TimeSpan che specifica la differenza massima di tempo tra gli orologi di sistema delle due parti che stanno comunicando.</span><span class="sxs-lookup"><span data-stu-id="a65fc-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="a65fc-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="a65fc-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="a65fc-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="a65fc-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="a65fc-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-132">Numero massimo di connessioni in sospeso nel servizio.</span><span class="sxs-lookup"><span data-stu-id="a65fc-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="a65fc-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="a65fc-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="a65fc-134">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="a65fc-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="a65fc-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-136">Numero di negoziazioni di sicurezza che possono essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a65fc-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="a65fc-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="a65fc-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="a65fc-138">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-140">TimeSpan che specifica la durata massima della fase di negoziazione della protezione tra server e client.</span><span class="sxs-lookup"><span data-stu-id="a65fc-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="a65fc-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="a65fc-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="a65fc-142">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="a65fc-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="a65fc-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-144">Valore booleano che specifica se le connessioni che utilizzano WS-Reliable Messaging tentano la riconnessione in caso di errori del trasporto.</span><span class="sxs-lookup"><span data-stu-id="a65fc-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="a65fc-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="a65fc-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="a65fc-146">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="a65fc-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="a65fc-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-148">Numero di parametri nonce utilizzato per il rilevamento degli attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="a65fc-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="a65fc-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="a65fc-149">ReplayWindow</span></span>  
 <span data-ttu-id="a65fc-150">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-152">TimeSpan che specifica la durata di validità dei singoli nonce dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a65fc-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="a65fc-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="a65fc-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="a65fc-154">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-156">Timespan che specifica l'intervallo di tempo dopo il quale l'iniziatore rinnova la chiave per la sessione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a65fc-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="a65fc-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="a65fc-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="a65fc-158">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-159">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-160">TimeSpan che specifica l'intervallo di tempo per il quale la chiave della sessione precedente è valida nei messaggi in arrivo durante un rinnovo della chiave.</span><span class="sxs-lookup"><span data-stu-id="a65fc-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="a65fc-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="a65fc-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="a65fc-162">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a65fc-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="a65fc-163">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a65fc-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a65fc-164">TimeSpan che specifica il periodo di validità di un timestamp.</span><span class="sxs-lookup"><span data-stu-id="a65fc-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a65fc-165">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a65fc-165">Requirements</span></span>  
  
|<span data-ttu-id="a65fc-166">MOF</span><span class="sxs-lookup"><span data-stu-id="a65fc-166">MOF</span></span>|<span data-ttu-id="a65fc-167">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a65fc-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a65fc-168">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a65fc-168">Namespace</span></span>|<span data-ttu-id="a65fc-169">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a65fc-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a65fc-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a65fc-170">See also</span></span>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
