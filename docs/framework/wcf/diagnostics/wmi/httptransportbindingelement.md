---
title: HttpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b1542406caf9bb3684ccf2d97ed441f1dc3d0db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="c5146-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c5146-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="c5146-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c5146-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5146-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5146-104">Syntax</span></span>  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c5146-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c5146-105">Methods</span></span>  
 <span data-ttu-id="c5146-106">La classe HttpTransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c5146-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c5146-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c5146-107">Properties</span></span>  
 <span data-ttu-id="c5146-108">La classe HttpTransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5146-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="c5146-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="c5146-109">AllowCookies</span></span>  
 <span data-ttu-id="c5146-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c5146-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="c5146-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-112">Valore che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="c5146-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="c5146-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="c5146-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="c5146-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c5146-114">Data type: string</span></span>  
  
 <span data-ttu-id="c5146-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-116">Schema di autenticazione utilizzato per autenticare le richieste del client da elaborare mediante un listener HTTP.</span><span class="sxs-lookup"><span data-stu-id="c5146-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="c5146-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="c5146-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="c5146-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c5146-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c5146-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-120">Valore che indica se i proxy vengono ignorati per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="c5146-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="c5146-121">HostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="c5146-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="c5146-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c5146-122">Data type: string</span></span>  
  
 <span data-ttu-id="c5146-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-124">Valore che indica se viene usato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.</span><span class="sxs-lookup"><span data-stu-id="c5146-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="c5146-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="c5146-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="c5146-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c5146-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="c5146-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-128">Se attivato, le connessioni HTTP vengono mantenute attive indipendentemente dal livello di attività.</span><span class="sxs-lookup"><span data-stu-id="c5146-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="c5146-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="c5146-129">MaxBufferSize</span></span>  
 <span data-ttu-id="c5146-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c5146-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="c5146-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-132">Dimensione massima del pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="c5146-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="c5146-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="c5146-133">ProxyAddress</span></span>  
 <span data-ttu-id="c5146-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c5146-134">Data type: string</span></span>  
  
 <span data-ttu-id="c5146-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-136">URI contenente l'indirizzo del proxy da utilizzare per le richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="c5146-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="c5146-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="c5146-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="c5146-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c5146-138">Data type: string</span></span>  
  
 <span data-ttu-id="c5146-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-140">Schema di autenticazione utilizzato per autenticare le richieste del client da elaborare mediante un listener HTTP.</span><span class="sxs-lookup"><span data-stu-id="c5146-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="c5146-141">Realm</span><span class="sxs-lookup"><span data-stu-id="c5146-141">Realm</span></span>  
 <span data-ttu-id="c5146-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c5146-142">Data type: string</span></span>  
  
 <span data-ttu-id="c5146-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-144">Area di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c5146-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="c5146-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="c5146-145">TransferMode</span></span>  
 <span data-ttu-id="c5146-146">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c5146-146">Data type: string</span></span>  
  
 <span data-ttu-id="c5146-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-148">Valore che specifica se i messaggi vengono memorizzati nel buffer o trasmessi in caso di richiesta o risposta.</span><span class="sxs-lookup"><span data-stu-id="c5146-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="c5146-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="c5146-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="c5146-150">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c5146-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="c5146-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-152">Valore che indica se sul server è attivata la condivisione di connessioni non sicure.</span><span class="sxs-lookup"><span data-stu-id="c5146-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="c5146-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="c5146-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="c5146-154">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c5146-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="c5146-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c5146-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c5146-156">Valore che indica se vengono utilizzate impostazioni proxy a livello di computer invece delle specifiche impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="c5146-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5146-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5146-157">Requirements</span></span>  
  
|<span data-ttu-id="c5146-158">MOF</span><span class="sxs-lookup"><span data-stu-id="c5146-158">MOF</span></span>|<span data-ttu-id="c5146-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c5146-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c5146-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c5146-160">Namespace</span></span>|<span data-ttu-id="c5146-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c5146-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5146-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5146-162">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
