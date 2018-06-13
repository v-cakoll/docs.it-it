---
title: Specifica del manifesto del provider
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: 02faee9ad69bd75f4df608b9a4767560945c7bb3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767141"
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="db2e2-102">Specifica del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-102">Provider Manifest Specification</span></span>
<span data-ttu-id="db2e2-103">Questa sezione illustra come un provider dell'archivio dati può supportare i tipi e le funzioni di tale archivio.</span><span class="sxs-lookup"><span data-stu-id="db2e2-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="db2e2-104">I servizi di entità funzionano indipendentemente da un provider dell'archivio dati specifico, tuttavia consentono comunque a un provider di dati di definire in modo esplicito l'interazione di modelli, mapping e query con un archivio dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="db2e2-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="db2e2-105">Su un piano prettamente pratico, i servizi di entità potrebbero essere destinati solo a un provider di dati o a un archivio dati specifico.</span><span class="sxs-lookup"><span data-stu-id="db2e2-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="db2e2-106">I tipi supportati dal provider sono supportati direttamente o indirettamente dal database sottostante.</span><span class="sxs-lookup"><span data-stu-id="db2e2-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="db2e2-107">Tali tipi no sono necessariamente i tipi di archivio, bensì i tipi usati dal provider per supportare [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db2e2-107">These types are not necessarily the exact store types, but the types the provider uses to support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="db2e2-108">I tipi di archivio/provider vengono descritti in termini EDM (Entity Data Model).</span><span class="sxs-lookup"><span data-stu-id="db2e2-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="db2e2-109">I tipi di parametri e i tipi restituiti per le funzioni supportate dall'archivio dati vengono specificati in termini EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db2e2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db2e2-110">Requirements</span></span>  
 <span data-ttu-id="db2e2-111">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e l'archivio dati devono essere in grado di passare i dati da e verso tipi noti senza troncamento o perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="db2e2-111">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="db2e2-112">Il manifesto del provider deve essere caricabile dagli strumenti in fase di progettazione senza che sia necessario aprire una connessione all'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="db2e2-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="db2e2-113">Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] avviene sensibili, ma potrebbe non essere nell'archivio dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="db2e2-113">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="db2e2-114">Quando nel manifesto vengono definiti e usati gli elementi di EDM, ad esempio identificatori e nomi dei tipi, è necessario che venga usata la distinzione tra maiuscole e minuscole di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db2e2-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] case sensitivity.</span></span> <span data-ttu-id="db2e2-115">Se nel manifesto del provider vengono visualizzati elementi dell'archivio dati per cui potrebbe essere rilevata la distinzione tra maiuscole e minuscole, è necessario mantenere tale distinzione nel manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="db2e2-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="db2e2-116">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] richiede un manifesto del provider per tutti i provider di dati.</span><span class="sxs-lookup"><span data-stu-id="db2e2-116">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] requires a provider manifest for all data providers.</span></span> <span data-ttu-id="db2e2-117">Se si tenta di utilizzare un provider che non dispone di un provider del manifesto con il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="db2e2-117">If you try to use a provider that does not have a provider manifest with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you will get an error.</span></span>  
  
 <span data-ttu-id="db2e2-118">Nella tabella seguente vengono descritti i tipi di eccezioni che verrebbero generati da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] quando l'interazione del provider genera eccezioni:</span><span class="sxs-lookup"><span data-stu-id="db2e2-118">The following table describes the kinds of exceptions the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="db2e2-119">Problema</span><span class="sxs-lookup"><span data-stu-id="db2e2-119">Issue</span></span>|<span data-ttu-id="db2e2-120">Eccezione</span><span class="sxs-lookup"><span data-stu-id="db2e2-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="db2e2-121">Il provider non supporta GetProviderManifest in DbProviderServices.</span><span class="sxs-lookup"><span data-stu-id="db2e2-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="db2e2-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="db2e2-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="db2e2-123">Manifesto del provider mancante: il provider restituisce `null` se si prova a recuperare il manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="db2e2-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="db2e2-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="db2e2-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="db2e2-125">Manifesto del provider non valido: il provider restituisce un XML non valido se si prova a recuperare il manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="db2e2-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="db2e2-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="db2e2-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="db2e2-127">Scenari</span><span class="sxs-lookup"><span data-stu-id="db2e2-127">Scenarios</span></span>  
 <span data-ttu-id="db2e2-128">Un provider deve supportare gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="db2e2-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="db2e2-129">Scrittura di un provider con mapping dei tipi simmetrico</span><span class="sxs-lookup"><span data-stu-id="db2e2-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="db2e2-130">È possibile scrivere un provider per il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] in cui ogni tipo di archivio esegue il mapping a un solo tipo EDM, indipendentemente dalla direzione del mapping.</span><span class="sxs-lookup"><span data-stu-id="db2e2-130">You can write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="db2e2-131">Per un tipo di provider che presenta un mapping molto semplice che corrisponde a un tipo EDM, è possibile usare una soluzione simmetrica, in quanto il sistema dei tipi è semplice o corrisponde ai tipi EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="db2e2-132">È possibile usare la semplicità del dominio e produrre un manifesto del provider dichiarativo statico.</span><span class="sxs-lookup"><span data-stu-id="db2e2-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="db2e2-133">Scrivere un file XML con due sezioni:</span><span class="sxs-lookup"><span data-stu-id="db2e2-133">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="db2e2-134">Un elenco di tipi di provider espresso in termini di "controparte EDM" di una funzione o di un tipo di archivio.</span><span class="sxs-lookup"><span data-stu-id="db2e2-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="db2e2-135">I tipi di archivio presentano tipi EDM della controparte.</span><span class="sxs-lookup"><span data-stu-id="db2e2-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="db2e2-136">Le funzioni di archivio presentano funzioni EDM corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="db2e2-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="db2e2-137">Ad esempio, varchar è un tipo SQL Server ma il tipo EDM corrispondente è stringa.</span><span class="sxs-lookup"><span data-stu-id="db2e2-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
-   <span data-ttu-id="db2e2-138">Un elenco di funzioni supportate dal provider in cui i tipi di parametri e i tipi restituiti sono espressi in termini EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="db2e2-139">Scrittura di un provider con mapping dei tipi asimmetrico</span><span class="sxs-lookup"><span data-stu-id="db2e2-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="db2e2-140">Quando si scrive un provider dell'archivio dati per [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], è possibile che per alcuni tipi il mapping da EDM al tipo di provider sia diverso da quello dal provider al tipo EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-140">When writing a data store provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="db2e2-141">Ad esempio, PrimitiveTypeKind.String EDM potrebbe essere mappato a nvarchar (4000) sul provider, mentre nvarchar (4000) viene mappato a PrimitiveTypeKind.String(MaxLength=4000) EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="db2e2-142">Scrivere un file XML con due sezioni:</span><span class="sxs-lookup"><span data-stu-id="db2e2-142">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="db2e2-143">Un elenco di tipi di provider espresso in termini EDM con la definizione del mapping per entrambe le direzioni: da EDM a provider e da provider a EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
-   <span data-ttu-id="db2e2-144">Un elenco di funzioni supportate dal provider in cui i tipi di parametri e i tipi restituiti sono espressi in termini EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="db2e2-145">Individuabilità del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="db2e2-146">Il manifesto viene usato indirettamente da diversi tipi di componenti nei servizi di entità, ad esempio strumenti o query, ma più direttamente viene usato dai metadati tramite l'uso del caricatore di metadati dell'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="db2e2-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="db2e2-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="db2e2-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="db2e2-148">È tuttavia possibile che un provider specificato supporti archivi diversi o versioni diverse dello stesso archivio.</span><span class="sxs-lookup"><span data-stu-id="db2e2-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="db2e2-149">È necessario pertanto che per ogni archivio dati supportato dal provider sia indicato un manifesto diverso.</span><span class="sxs-lookup"><span data-stu-id="db2e2-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="db2e2-150">Token del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="db2e2-151">Quando viene aperta una connessione a un archivio dati, il provider può richiedere informazioni tramite query per ottenere il manifesto appropriato.</span><span class="sxs-lookup"><span data-stu-id="db2e2-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="db2e2-152">Questa operazione potrebbe non essere possibile negli scenari offline in cui le informazioni di connessione non sono disponibili oppure quando non è possibile eseguire la connessione all'archivio.</span><span class="sxs-lookup"><span data-stu-id="db2e2-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="db2e2-153">Identificare il manifesto tramite l'attributo `ProviderManifestToken` dell'elemento `Schema` nel file con estensione ssdl.</span><span class="sxs-lookup"><span data-stu-id="db2e2-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="db2e2-154">Non esiste un formato obbligatorio per questo attributo. Il provider sceglie le informazioni minime necessarie che consentono di identificare un manifesto senza dover aprire una connessione all'archivio.</span><span class="sxs-lookup"><span data-stu-id="db2e2-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="db2e2-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="db2e2-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="db2e2-156">Modello di programmazione del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="db2e2-157">I provider derivano da <xref:System.Data.Common.DbXmlEnabledProviderManifest>, che consente loro di specificare in modo dichiarativo i propri manifesti.</span><span class="sxs-lookup"><span data-stu-id="db2e2-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="db2e2-158">Nell'illustrazione seguente viene mostrata la gerarchia di classi di un provider:</span><span class="sxs-lookup"><span data-stu-id="db2e2-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="db2e2-159">![Nessuna](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="db2e2-159">![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="db2e2-160">API di individuabilità</span><span class="sxs-lookup"><span data-stu-id="db2e2-160">Discoverability API</span></span>  
 <span data-ttu-id="db2e2-161">Il manifesto del provider viene caricato dal caricatore dei metadati dell'archivio (StoreItemCollection) tramite una connessione all'archivio dati o un token del manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="db2e2-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="db2e2-162">Uso di una connessione all'archivio dati</span><span class="sxs-lookup"><span data-stu-id="db2e2-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="db2e2-163">Quando è disponibile la connessione all'archivio dati, chiamare DbProvderServices.GetProviderManifestToken per restituire il token passato al metodo GetProviderManifest, che restituisce DbProviderManifest.</span><span class="sxs-lookup"><span data-stu-id="db2e2-163">When the data store connection is available, call DbProvderServices.GetProviderManifestToken to return the token that is passed to the GetProviderManifest method, which returns DbProviderManifest.</span></span> <span data-ttu-id="db2e2-164">Tale metodo funge da delegato per l'implementazione del provider di GetDbProviderManifestToken.</span><span class="sxs-lookup"><span data-stu-id="db2e2-164">This method delegates to the provider's implementation of GetDbProviderManifestToken.</span></span>  
  
```  
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="db2e2-165">Uso di un token del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="db2e2-166">Per lo scenario offline il token viene scelto dalla rappresentazione SSDL.</span><span class="sxs-lookup"><span data-stu-id="db2e2-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="db2e2-167">il SSDL consente di specificare un ProviderManifestToken (vedere [elemento dello Schema (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222) per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="db2e2-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222) for more information).</span></span> <span data-ttu-id="db2e2-168">Se ad esempio non è possibile aprire una connessione, in SSDL è disponibile un token del manifesto del provider che specifica informazioni sul manifesto.</span><span class="sxs-lookup"><span data-stu-id="db2e2-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="db2e2-169">Schema del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="db2e2-170">Lo schema di informazioni definito per ogni provider contiene le informazioni statiche che devono essere usate dai metadati:</span><span class="sxs-lookup"><span data-stu-id="db2e2-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a><span data-ttu-id="db2e2-171">Nodo Types</span><span class="sxs-lookup"><span data-stu-id="db2e2-171">Types Node</span></span>  
 <span data-ttu-id="db2e2-172">Il nodo Types nel manifesto del provider contiene informazioni sugli oggetti Types supportati a livello nativo dall'archivio dati o tramite il provider.</span><span class="sxs-lookup"><span data-stu-id="db2e2-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="db2e2-173">Nodo Type</span><span class="sxs-lookup"><span data-stu-id="db2e2-173">Type Node</span></span>  
 <span data-ttu-id="db2e2-174">Ogni nodo Type definisce un tipo di provider in termini di EDM.</span><span class="sxs-lookup"><span data-stu-id="db2e2-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="db2e2-175">Il nodo Type descrive il nome del tipo di provider, informazioni correlate al tipo di modello al quale viene mappato, nonché facet per descrivere il mapping dei tipi specifico.</span><span class="sxs-lookup"><span data-stu-id="db2e2-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="db2e2-176">Per esprimere queste informazioni sui tipi nel manifesto del provider, è necessario che ogni dichiarazione TypeInformation definisca diverse descrizioni di facet per ogni oggetto Type:</span><span class="sxs-lookup"><span data-stu-id="db2e2-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="db2e2-177">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="db2e2-177">Attribute Name</span></span>|<span data-ttu-id="db2e2-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db2e2-178">Data Type</span></span>|<span data-ttu-id="db2e2-179">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="db2e2-179">Required</span></span>|<span data-ttu-id="db2e2-180">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="db2e2-180">Default Value</span></span>|<span data-ttu-id="db2e2-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db2e2-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="db2e2-182">Nome</span><span class="sxs-lookup"><span data-stu-id="db2e2-182">Name</span></span>|<span data-ttu-id="db2e2-183">String</span><span class="sxs-lookup"><span data-stu-id="db2e2-183">String</span></span>|<span data-ttu-id="db2e2-184">Sì</span><span class="sxs-lookup"><span data-stu-id="db2e2-184">Yes</span></span>|<span data-ttu-id="db2e2-185">n/d</span><span class="sxs-lookup"><span data-stu-id="db2e2-185">n/a</span></span>|<span data-ttu-id="db2e2-186">Nome del tipo di dati specifico del provider</span><span class="sxs-lookup"><span data-stu-id="db2e2-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="db2e2-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="db2e2-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="db2e2-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="db2e2-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="db2e2-189">Sì</span><span class="sxs-lookup"><span data-stu-id="db2e2-189">Yes</span></span>|<span data-ttu-id="db2e2-190">n/d</span><span class="sxs-lookup"><span data-stu-id="db2e2-190">n/a</span></span>|<span data-ttu-id="db2e2-191">Nome del tipo EDM</span><span class="sxs-lookup"><span data-stu-id="db2e2-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="db2e2-192">Nodo Function</span><span class="sxs-lookup"><span data-stu-id="db2e2-192">Function Node</span></span>  
 <span data-ttu-id="db2e2-193">Ogni oggetto Function definisce una sola funzione disponibile tramite il provider.</span><span class="sxs-lookup"><span data-stu-id="db2e2-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="db2e2-194">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="db2e2-194">Attribute Name</span></span>|<span data-ttu-id="db2e2-195">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db2e2-195">Data Type</span></span>|<span data-ttu-id="db2e2-196">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="db2e2-196">Required</span></span>|<span data-ttu-id="db2e2-197">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="db2e2-197">Default Value</span></span>|<span data-ttu-id="db2e2-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db2e2-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="db2e2-199">Nome</span><span class="sxs-lookup"><span data-stu-id="db2e2-199">Name</span></span>|<span data-ttu-id="db2e2-200">String</span><span class="sxs-lookup"><span data-stu-id="db2e2-200">String</span></span>|<span data-ttu-id="db2e2-201">Sì</span><span class="sxs-lookup"><span data-stu-id="db2e2-201">Yes</span></span>|<span data-ttu-id="db2e2-202">n/d</span><span class="sxs-lookup"><span data-stu-id="db2e2-202">n/a</span></span>|<span data-ttu-id="db2e2-203">Nome/identificatore della funzione</span><span class="sxs-lookup"><span data-stu-id="db2e2-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="db2e2-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="db2e2-204">ReturnType</span></span>|<span data-ttu-id="db2e2-205">String</span><span class="sxs-lookup"><span data-stu-id="db2e2-205">String</span></span>|<span data-ttu-id="db2e2-206">No</span><span class="sxs-lookup"><span data-stu-id="db2e2-206">No</span></span>|<span data-ttu-id="db2e2-207">Void</span><span class="sxs-lookup"><span data-stu-id="db2e2-207">Void</span></span>|<span data-ttu-id="db2e2-208">Il tipo restituito EDM della funzione</span><span class="sxs-lookup"><span data-stu-id="db2e2-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="db2e2-209">Aggregate</span><span class="sxs-lookup"><span data-stu-id="db2e2-209">Aggregate</span></span>|<span data-ttu-id="db2e2-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="db2e2-210">Boolean</span></span>|<span data-ttu-id="db2e2-211">No</span><span class="sxs-lookup"><span data-stu-id="db2e2-211">No</span></span>|<span data-ttu-id="db2e2-212">False</span><span class="sxs-lookup"><span data-stu-id="db2e2-212">False</span></span>|<span data-ttu-id="db2e2-213">Restituisce True se si tratta di una funzione di aggregazione</span><span class="sxs-lookup"><span data-stu-id="db2e2-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="db2e2-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="db2e2-214">BuiltIn</span></span>|<span data-ttu-id="db2e2-215">Boolean</span><span class="sxs-lookup"><span data-stu-id="db2e2-215">Boolean</span></span>|<span data-ttu-id="db2e2-216">No</span><span class="sxs-lookup"><span data-stu-id="db2e2-216">No</span></span>|<span data-ttu-id="db2e2-217">True</span><span class="sxs-lookup"><span data-stu-id="db2e2-217">True</span></span>|<span data-ttu-id="db2e2-218">Restituisce True se la funzione è inclusa nell'archivio dati</span><span class="sxs-lookup"><span data-stu-id="db2e2-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="db2e2-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="db2e2-219">StoreFunctionName</span></span>|<span data-ttu-id="db2e2-220">String</span><span class="sxs-lookup"><span data-stu-id="db2e2-220">String</span></span>|<span data-ttu-id="db2e2-221">No</span><span class="sxs-lookup"><span data-stu-id="db2e2-221">No</span></span>|<span data-ttu-id="db2e2-222">\<Nome ></span><span class="sxs-lookup"><span data-stu-id="db2e2-222">\<Name></span></span>|<span data-ttu-id="db2e2-223">Nome della funzione nell'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="db2e2-223">Function Name in the data store.</span></span>  <span data-ttu-id="db2e2-224">Consente di eseguire un determinato tipo di reindirizzamento dei nomi delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="db2e2-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="db2e2-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="db2e2-225">NiladicFunction</span></span>|<span data-ttu-id="db2e2-226">Boolean</span><span class="sxs-lookup"><span data-stu-id="db2e2-226">Boolean</span></span>|<span data-ttu-id="db2e2-227">No</span><span class="sxs-lookup"><span data-stu-id="db2e2-227">No</span></span>|<span data-ttu-id="db2e2-228">False</span><span class="sxs-lookup"><span data-stu-id="db2e2-228">False</span></span>|<span data-ttu-id="db2e2-229">Restituisce True se la funzione non richiede parametri e viene chiamata senza parametri</span><span class="sxs-lookup"><span data-stu-id="db2e2-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="db2e2-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="db2e2-230">ParameterType</span></span><br /><br /> <span data-ttu-id="db2e2-231">Semantics</span><span class="sxs-lookup"><span data-stu-id="db2e2-231">Semantics</span></span>|<span data-ttu-id="db2e2-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="db2e2-232">ParameterSemantics</span></span>|<span data-ttu-id="db2e2-233">No</span><span class="sxs-lookup"><span data-stu-id="db2e2-233">No</span></span>|<span data-ttu-id="db2e2-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="db2e2-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="db2e2-235">Conversion</span><span class="sxs-lookup"><span data-stu-id="db2e2-235">Conversion</span></span>|<span data-ttu-id="db2e2-236">Scelta della modalità con cui la pipeline della query gestisce la sostituzione del tipo di parametro:</span><span class="sxs-lookup"><span data-stu-id="db2e2-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="db2e2-237">-ExactMatchOnly</span><span class="sxs-lookup"><span data-stu-id="db2e2-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="db2e2-238">-AllowImplicitPromotion</span><span class="sxs-lookup"><span data-stu-id="db2e2-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="db2e2-239">-AllowImplicitConversion</span><span class="sxs-lookup"><span data-stu-id="db2e2-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="db2e2-240">**Nodo parametri**</span><span class="sxs-lookup"><span data-stu-id="db2e2-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="db2e2-241">Ogni funzione presenta una raccolta di uno o più nodi Parameter.</span><span class="sxs-lookup"><span data-stu-id="db2e2-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="db2e2-242">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="db2e2-242">Attribute Name</span></span>|<span data-ttu-id="db2e2-243">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="db2e2-243">Data Type</span></span>|<span data-ttu-id="db2e2-244">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="db2e2-244">Required</span></span>|<span data-ttu-id="db2e2-245">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="db2e2-245">Default Value</span></span>|<span data-ttu-id="db2e2-246">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db2e2-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="db2e2-247">Nome</span><span class="sxs-lookup"><span data-stu-id="db2e2-247">Name</span></span>|<span data-ttu-id="db2e2-248">String</span><span class="sxs-lookup"><span data-stu-id="db2e2-248">String</span></span>|<span data-ttu-id="db2e2-249">Sì</span><span class="sxs-lookup"><span data-stu-id="db2e2-249">Yes</span></span>|<span data-ttu-id="db2e2-250">n/d</span><span class="sxs-lookup"><span data-stu-id="db2e2-250">n/a</span></span>|<span data-ttu-id="db2e2-251">Nome/identificatore del parametro.</span><span class="sxs-lookup"><span data-stu-id="db2e2-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="db2e2-252">Tipo</span><span class="sxs-lookup"><span data-stu-id="db2e2-252">Type</span></span>|<span data-ttu-id="db2e2-253">String</span><span class="sxs-lookup"><span data-stu-id="db2e2-253">String</span></span>|<span data-ttu-id="db2e2-254">Sì</span><span class="sxs-lookup"><span data-stu-id="db2e2-254">Yes</span></span>|<span data-ttu-id="db2e2-255">n/d</span><span class="sxs-lookup"><span data-stu-id="db2e2-255">n/a</span></span>|<span data-ttu-id="db2e2-256">Tipo EDM del parametro.</span><span class="sxs-lookup"><span data-stu-id="db2e2-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="db2e2-257">Modalità</span><span class="sxs-lookup"><span data-stu-id="db2e2-257">Mode</span></span>|<span data-ttu-id="db2e2-258">Parametro</span><span class="sxs-lookup"><span data-stu-id="db2e2-258">Parameter</span></span><br /><br /> <span data-ttu-id="db2e2-259">Direzione</span><span class="sxs-lookup"><span data-stu-id="db2e2-259">Direction</span></span>|<span data-ttu-id="db2e2-260">Sì</span><span class="sxs-lookup"><span data-stu-id="db2e2-260">Yes</span></span>|<span data-ttu-id="db2e2-261">n/d</span><span class="sxs-lookup"><span data-stu-id="db2e2-261">n/a</span></span>|<span data-ttu-id="db2e2-262">Direzione del parametro:</span><span class="sxs-lookup"><span data-stu-id="db2e2-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="db2e2-263">-   in</span><span class="sxs-lookup"><span data-stu-id="db2e2-263">-   in</span></span><br /><span data-ttu-id="db2e2-264">-out</span><span class="sxs-lookup"><span data-stu-id="db2e2-264">-   out</span></span><br /><span data-ttu-id="db2e2-265">-inout</span><span class="sxs-lookup"><span data-stu-id="db2e2-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="db2e2-266">Attributo namespace</span><span class="sxs-lookup"><span data-stu-id="db2e2-266">Namespace Attribute</span></span>  
 <span data-ttu-id="db2e2-267">Ogni provider dell'archivio dati deve definire uno spazio dei nomi o un gruppo di spazi dei nomi per le informazioni definite nel manifesto.</span><span class="sxs-lookup"><span data-stu-id="db2e2-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="db2e2-268">Tale spazio dei nomi può essere usato nelle query Entity SQL per risolvere nomi di funzioni e tipi.</span><span class="sxs-lookup"><span data-stu-id="db2e2-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="db2e2-269">Ad esempio: SqlServer.</span><span class="sxs-lookup"><span data-stu-id="db2e2-269">For instance: SqlServer.</span></span> <span data-ttu-id="db2e2-270">Lo spazio dei nomi deve essere diverso dallo spazio dei nomi canonico, ovvero EDM, definito dai servizi di entità per funzioni standard che devono essere supportate dalle query Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="db2e2-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2e2-271">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db2e2-271">See Also</span></span>  
 [<span data-ttu-id="db2e2-272">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="db2e2-272">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
