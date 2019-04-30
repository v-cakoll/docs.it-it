---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957014"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="4408d-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="4408d-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="4408d-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="4408d-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4408d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4408d-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4408d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4408d-105">Methods</span></span>  
 <span data-ttu-id="4408d-106">La classe ServiceBehaviorAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4408d-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4408d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4408d-107">Properties</span></span>  
 <span data-ttu-id="4408d-108">La classe ServiceBehaviorAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4408d-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="4408d-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="4408d-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="4408d-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-112">Indica se chiudere automaticamente una sessione quando un client chiude una sessione di output.</span><span class="sxs-lookup"><span data-stu-id="4408d-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="4408d-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="4408d-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="4408d-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4408d-114">Data type: string</span></span>  
<span data-ttu-id="4408d-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-116">Indica se un servizio supporta un solo thread, più thread o chiamate rientranti.</span><span class="sxs-lookup"><span data-stu-id="4408d-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="4408d-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="4408d-117">ConfigurationName</span></span>  
 <span data-ttu-id="4408d-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4408d-118">Data type: string</span></span>  
  
 <span data-ttu-id="4408d-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-120">Nome della configurazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="4408d-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="4408d-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="4408d-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="4408d-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-124">Specifica se inviare dati di serializzazione sconosciuti in transito.</span><span class="sxs-lookup"><span data-stu-id="4408d-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="4408d-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="4408d-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="4408d-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-128">Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="4408d-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="4408d-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="4408d-129">InstanceContextMode</span></span>  
 <span data-ttu-id="4408d-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4408d-130">Data type: string</span></span>  
  
 <span data-ttu-id="4408d-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-132">Specifica quando viene creato un nuovo oggetto servizio.</span><span class="sxs-lookup"><span data-stu-id="4408d-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="4408d-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="4408d-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="4408d-134">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="4408d-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="4408d-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-136">Numero massimo di elementi consentiti in un oggetto serializzato.</span><span class="sxs-lookup"><span data-stu-id="4408d-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="4408d-137">Nome</span><span class="sxs-lookup"><span data-stu-id="4408d-137">Name</span></span>  
 <span data-ttu-id="4408d-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4408d-138">Data type: string</span></span>  
  
 <span data-ttu-id="4408d-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-140">Attributo nome del servizio in WSDL.</span><span class="sxs-lookup"><span data-stu-id="4408d-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="4408d-141">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4408d-141">Namespace</span></span>  
 <span data-ttu-id="4408d-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4408d-142">Data type: string</span></span>  
  
 <span data-ttu-id="4408d-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-144">Spazio dei nomi di destinazione del servizio in WSDL.</span><span class="sxs-lookup"><span data-stu-id="4408d-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="4408d-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="4408d-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="4408d-146">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-148">Specifica se l'oggetto servizio viene riciclato al completamento della transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="4408d-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="4408d-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="4408d-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="4408d-150">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-152">Specifica se alla chiusura della sessione corrente vengono completate le transazioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="4408d-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="4408d-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="4408d-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="4408d-154">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4408d-154">Data type: string</span></span>  
  
 <span data-ttu-id="4408d-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-156">Specifica il livello di isolamento della transazione.</span><span class="sxs-lookup"><span data-stu-id="4408d-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="4408d-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="4408d-157">TransactionTimeout</span></span>  
 <span data-ttu-id="4408d-158">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="4408d-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="4408d-159">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-160">Periodo entro il quale una transazione deve essere completata.</span><span class="sxs-lookup"><span data-stu-id="4408d-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="4408d-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="4408d-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="4408d-162">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-163">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-164">Specifica se utilizzare il contesto di sincronizzazione corrente per scegliere l'esecuzione del thread.</span><span class="sxs-lookup"><span data-stu-id="4408d-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="4408d-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="4408d-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="4408d-166">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4408d-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="4408d-167">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4408d-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4408d-168">Specifica se il sistema o l'applicazione impone l'elaborazione delle intestazioni MustUnderstand SOAP.</span><span class="sxs-lookup"><span data-stu-id="4408d-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4408d-169">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4408d-169">Requirements</span></span>  
  
|<span data-ttu-id="4408d-170">MOF</span><span class="sxs-lookup"><span data-stu-id="4408d-170">MOF</span></span>|<span data-ttu-id="4408d-171">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4408d-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4408d-172">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4408d-172">Namespace</span></span>|<span data-ttu-id="4408d-173">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4408d-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4408d-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4408d-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
