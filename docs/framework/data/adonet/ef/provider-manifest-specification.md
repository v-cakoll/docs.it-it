---
title: Specifica del manifesto del provider
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: cc58bbc82f3930f087b5da0c64afb4f9f03e905b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854494"
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="50b73-102">Specifica del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-102">Provider Manifest Specification</span></span>
<span data-ttu-id="50b73-103">Questa sezione illustra come un provider dell'archivio dati può supportare i tipi e le funzioni di tale archivio.</span><span class="sxs-lookup"><span data-stu-id="50b73-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="50b73-104">I servizi di entità funzionano indipendentemente da un provider dell'archivio dati specifico, tuttavia consentono comunque a un provider di dati di definire in modo esplicito l'interazione di modelli, mapping e query con un archivio dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="50b73-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="50b73-105">Su un piano prettamente pratico, i servizi di entità potrebbero essere destinati solo a un provider di dati o a un archivio dati specifico.</span><span class="sxs-lookup"><span data-stu-id="50b73-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="50b73-106">I tipi supportati dal provider sono supportati direttamente o indirettamente dal database sottostante.</span><span class="sxs-lookup"><span data-stu-id="50b73-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="50b73-107">Questi tipi non sono necessariamente i tipi di archivio esatti, ma i tipi utilizzati dal provider per supportare il Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="50b73-107">These types are not necessarily the exact store types, but the types the provider uses to support the Entity Framework.</span></span> <span data-ttu-id="50b73-108">I tipi di archivio/provider vengono descritti in termini EDM (Entity Data Model).</span><span class="sxs-lookup"><span data-stu-id="50b73-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="50b73-109">I tipi di parametri e i tipi restituiti per le funzioni supportate dall'archivio dati vengono specificati in termini EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b73-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50b73-110">Requirements</span></span>  
 <span data-ttu-id="50b73-111">Il Entity Framework e l'archivio dati devono essere in grado di passare i dati nei tipi noti senza alcuna perdita di dati o troncamento.</span><span class="sxs-lookup"><span data-stu-id="50b73-111">The Entity Framework and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="50b73-112">Il manifesto del provider deve essere caricabile dagli strumenti in fase di progettazione senza che sia necessario aprire una connessione all'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="50b73-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="50b73-113">Il Entity Framework fa distinzione tra maiuscole e minuscole, ma l'archivio dati sottostante potrebbe non essere.</span><span class="sxs-lookup"><span data-stu-id="50b73-113">The Entity Framework is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="50b73-114">Quando gli artefatti EDM, ad esempio identificatori e nomi di tipi, vengono definiti e utilizzati nel manifesto, è necessario che utilizzino la distinzione tra maiuscole e minuscole Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="50b73-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the Entity Framework case sensitivity.</span></span> <span data-ttu-id="50b73-115">Se nel manifesto del provider vengono visualizzati elementi dell'archivio dati per cui potrebbe essere rilevata la distinzione tra maiuscole e minuscole, è necessario mantenere tale distinzione nel manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="50b73-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="50b73-116">Il Entity Framework richiede un manifesto del provider per tutti i provider di dati.</span><span class="sxs-lookup"><span data-stu-id="50b73-116">The Entity Framework requires a provider manifest for all data providers.</span></span> <span data-ttu-id="50b73-117">Se si tenta di utilizzare un provider che non dispone di un manifesto del provider con il Entity Framework, verrà ricevuto un errore.</span><span class="sxs-lookup"><span data-stu-id="50b73-117">If you try to use a provider that does not have a provider manifest with the Entity Framework, you will get an error.</span></span>  
  
 <span data-ttu-id="50b73-118">Nella tabella seguente vengono descritti i tipi di eccezioni generate da Entity Framework quando si verificano eccezioni tramite l'interazione del provider:</span><span class="sxs-lookup"><span data-stu-id="50b73-118">The following table describes the kinds of exceptions the Entity Framework would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="50b73-119">Problema</span><span class="sxs-lookup"><span data-stu-id="50b73-119">Issue</span></span>|<span data-ttu-id="50b73-120">Eccezione</span><span class="sxs-lookup"><span data-stu-id="50b73-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="50b73-121">Il provider non supporta GetProviderManifest in DbProviderServices.</span><span class="sxs-lookup"><span data-stu-id="50b73-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="50b73-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="50b73-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="50b73-123">Manifesto del provider mancante: il provider restituisce `null` se si prova a recuperare il manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="50b73-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="50b73-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="50b73-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="50b73-125">Manifesto del provider non valido: il provider restituisce un XML non valido se si prova a recuperare il manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="50b73-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="50b73-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="50b73-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="50b73-127">Scenari</span><span class="sxs-lookup"><span data-stu-id="50b73-127">Scenarios</span></span>  
 <span data-ttu-id="50b73-128">Un provider deve supportare gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="50b73-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="50b73-129">Scrittura di un provider con mapping dei tipi simmetrico</span><span class="sxs-lookup"><span data-stu-id="50b73-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="50b73-130">È possibile scrivere un provider per la Entity Framework in cui ogni tipo di archivio esegue il mapping a un singolo tipo EDM, indipendentemente dalla direzione del mapping.</span><span class="sxs-lookup"><span data-stu-id="50b73-130">You can write a provider for the Entity Framework where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="50b73-131">Per un tipo di provider che presenta un mapping molto semplice che corrisponde a un tipo EDM, è possibile usare una soluzione simmetrica, in quanto il sistema dei tipi è semplice o corrisponde ai tipi EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="50b73-132">È possibile usare la semplicità del dominio e produrre un manifesto del provider dichiarativo statico.</span><span class="sxs-lookup"><span data-stu-id="50b73-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="50b73-133">Scrivere un file XML con due sezioni:</span><span class="sxs-lookup"><span data-stu-id="50b73-133">You write an XML file that has two sections:</span></span>  
  
- <span data-ttu-id="50b73-134">Un elenco di tipi di provider espresso in termini di "controparte EDM" di una funzione o di un tipo di archivio.</span><span class="sxs-lookup"><span data-stu-id="50b73-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="50b73-135">I tipi di archivio presentano tipi EDM della controparte.</span><span class="sxs-lookup"><span data-stu-id="50b73-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="50b73-136">Le funzioni di archivio presentano funzioni EDM corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="50b73-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="50b73-137">Ad esempio, varchar è un tipo SQL Server ma il tipo EDM corrispondente è stringa.</span><span class="sxs-lookup"><span data-stu-id="50b73-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
- <span data-ttu-id="50b73-138">Un elenco di funzioni supportate dal provider in cui i tipi di parametri e i tipi restituiti sono espressi in termini EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="50b73-139">Scrittura di un provider con mapping dei tipi asimmetrico</span><span class="sxs-lookup"><span data-stu-id="50b73-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="50b73-140">Quando si scrive un provider dell'archivio dati per la Entity Framework, il mapping del tipo EDM-to-provider per alcuni tipi può essere diverso dal mapping del tipo da provider a EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-140">When writing a data store provider for the Entity Framework, the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="50b73-141">Ad esempio, PrimitiveTypeKind.String EDM potrebbe essere mappato a nvarchar (4000) sul provider, mentre nvarchar (4000) viene mappato a PrimitiveTypeKind.String(MaxLength=4000) EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="50b73-142">Scrivere un file XML con due sezioni:</span><span class="sxs-lookup"><span data-stu-id="50b73-142">You write an XML file that has two sections:</span></span>  
  
- <span data-ttu-id="50b73-143">Elenco di tipi di provider espressi in termini EDM e definizione del mapping per entrambe le direzioni: Da EDM a provider e da provider a EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
- <span data-ttu-id="50b73-144">Un elenco di funzioni supportate dal provider in cui i tipi di parametri e i tipi restituiti sono espressi in termini EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="50b73-145">Individuabilità del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="50b73-146">Il manifesto viene usato indirettamente da diversi tipi di componenti nei servizi di entità, ad esempio strumenti o query, ma più direttamente viene usato dai metadati tramite l'uso del caricatore di metadati dell'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="50b73-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="50b73-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](./media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="50b73-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](./media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="50b73-148">È tuttavia possibile che un provider specificato supporti archivi diversi o versioni diverse dello stesso archivio.</span><span class="sxs-lookup"><span data-stu-id="50b73-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="50b73-149">È necessario pertanto che per ogni archivio dati supportato dal provider sia indicato un manifesto diverso.</span><span class="sxs-lookup"><span data-stu-id="50b73-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="50b73-150">Token del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="50b73-151">Quando viene aperta una connessione a un archivio dati, il provider può richiedere informazioni tramite query per ottenere il manifesto appropriato.</span><span class="sxs-lookup"><span data-stu-id="50b73-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="50b73-152">Questa operazione potrebbe non essere possibile negli scenari offline in cui le informazioni di connessione non sono disponibili oppure quando non è possibile eseguire la connessione all'archivio.</span><span class="sxs-lookup"><span data-stu-id="50b73-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="50b73-153">Identificare il manifesto tramite l'attributo `ProviderManifestToken` dell'elemento `Schema` nel file con estensione ssdl.</span><span class="sxs-lookup"><span data-stu-id="50b73-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="50b73-154">Non esiste un formato obbligatorio per questo attributo. Il provider sceglie le informazioni minime necessarie che consentono di identificare un manifesto senza dover aprire una connessione all'archivio.</span><span class="sxs-lookup"><span data-stu-id="50b73-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="50b73-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50b73-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="50b73-156">Modello di programmazione del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="50b73-157">I provider derivano da <xref:System.Data.Common.DbXmlEnabledProviderManifest>, che consente loro di specificare in modo dichiarativo i propri manifesti.</span><span class="sxs-lookup"><span data-stu-id="50b73-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="50b73-158">Nell'illustrazione seguente viene mostrata la gerarchia di classi di un provider:</span><span class="sxs-lookup"><span data-stu-id="50b73-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="50b73-159">![None](./media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="50b73-159">![None](./media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="50b73-160">API di individuabilità</span><span class="sxs-lookup"><span data-stu-id="50b73-160">Discoverability API</span></span>  
 <span data-ttu-id="50b73-161">Il manifesto del provider viene caricato dal caricatore dei metadati dell'archivio (StoreItemCollection) tramite una connessione all'archivio dati o un token del manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="50b73-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="50b73-162">Uso di una connessione all'archivio dati</span><span class="sxs-lookup"><span data-stu-id="50b73-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="50b73-163">Quando è disponibile la connessione all'archivio dati, <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType> chiamare per restituire il token passato <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A> al metodo, che restituisce <xref:System.Data.Common.DbProviderManifest>.</span><span class="sxs-lookup"><span data-stu-id="50b73-163">When the data store connection is available, call <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType> to return the token that is passed to the <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A> method, which returns <xref:System.Data.Common.DbProviderManifest>.</span></span> <span data-ttu-id="50b73-164">Questo metodo delega all'implementazione del provider di `GetDbProviderManifestToken`.</span><span class="sxs-lookup"><span data-stu-id="50b73-164">This method delegates to the provider's implementation of `GetDbProviderManifestToken`.</span></span>  
  
```csharp
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="50b73-165">Uso di un token del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="50b73-166">Per lo scenario offline il token viene scelto dalla rappresentazione SSDL.</span><span class="sxs-lookup"><span data-stu-id="50b73-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="50b73-167">Il linguaggio SSDL consente di specificare un ProviderManifestToken (vedere [elemento schema (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) per ulteriori informazioni).</span><span class="sxs-lookup"><span data-stu-id="50b73-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) for more information).</span></span> <span data-ttu-id="50b73-168">Se ad esempio non è possibile aprire una connessione, in SSDL è disponibile un token del manifesto del provider che specifica informazioni sul manifesto.</span><span class="sxs-lookup"><span data-stu-id="50b73-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="50b73-169">Schema del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="50b73-170">Lo schema di informazioni definito per ogni provider contiene le informazioni statiche che devono essere usate dai metadati:</span><span class="sxs-lookup"><span data-stu-id="50b73-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
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
  
#### <a name="types-node"></a><span data-ttu-id="50b73-171">Nodo Types</span><span class="sxs-lookup"><span data-stu-id="50b73-171">Types Node</span></span>  
 <span data-ttu-id="50b73-172">Il nodo Types nel manifesto del provider contiene informazioni sugli oggetti Types supportati a livello nativo dall'archivio dati o tramite il provider.</span><span class="sxs-lookup"><span data-stu-id="50b73-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="50b73-173">Nodo Type</span><span class="sxs-lookup"><span data-stu-id="50b73-173">Type Node</span></span>  
 <span data-ttu-id="50b73-174">Ogni nodo Type definisce un tipo di provider in termini di EDM.</span><span class="sxs-lookup"><span data-stu-id="50b73-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="50b73-175">Il nodo Type descrive il nome del tipo di provider, informazioni correlate al tipo di modello al quale viene mappato, nonché facet per descrivere il mapping dei tipi specifico.</span><span class="sxs-lookup"><span data-stu-id="50b73-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="50b73-176">Per esprimere queste informazioni sui tipi nel manifesto del provider, è necessario che ogni dichiarazione TypeInformation definisca diverse descrizioni di facet per ogni oggetto Type:</span><span class="sxs-lookup"><span data-stu-id="50b73-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="50b73-177">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="50b73-177">Attribute Name</span></span>|<span data-ttu-id="50b73-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="50b73-178">Data Type</span></span>|<span data-ttu-id="50b73-179">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="50b73-179">Required</span></span>|<span data-ttu-id="50b73-180">Default Value</span><span class="sxs-lookup"><span data-stu-id="50b73-180">Default Value</span></span>|<span data-ttu-id="50b73-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50b73-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="50b73-182">Name</span><span class="sxs-lookup"><span data-stu-id="50b73-182">Name</span></span>|<span data-ttu-id="50b73-183">String</span><span class="sxs-lookup"><span data-stu-id="50b73-183">String</span></span>|<span data-ttu-id="50b73-184">Sì</span><span class="sxs-lookup"><span data-stu-id="50b73-184">Yes</span></span>|<span data-ttu-id="50b73-185">n/d</span><span class="sxs-lookup"><span data-stu-id="50b73-185">n/a</span></span>|<span data-ttu-id="50b73-186">Nome del tipo di dati specifico del provider</span><span class="sxs-lookup"><span data-stu-id="50b73-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="50b73-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="50b73-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="50b73-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="50b73-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="50b73-189">Yes</span><span class="sxs-lookup"><span data-stu-id="50b73-189">Yes</span></span>|<span data-ttu-id="50b73-190">n/d</span><span class="sxs-lookup"><span data-stu-id="50b73-190">n/a</span></span>|<span data-ttu-id="50b73-191">Nome del tipo EDM</span><span class="sxs-lookup"><span data-stu-id="50b73-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="50b73-192">Nodo Function</span><span class="sxs-lookup"><span data-stu-id="50b73-192">Function Node</span></span>  
 <span data-ttu-id="50b73-193">Ogni oggetto Function definisce una sola funzione disponibile tramite il provider.</span><span class="sxs-lookup"><span data-stu-id="50b73-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="50b73-194">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="50b73-194">Attribute Name</span></span>|<span data-ttu-id="50b73-195">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="50b73-195">Data Type</span></span>|<span data-ttu-id="50b73-196">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="50b73-196">Required</span></span>|<span data-ttu-id="50b73-197">Default Value</span><span class="sxs-lookup"><span data-stu-id="50b73-197">Default Value</span></span>|<span data-ttu-id="50b73-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50b73-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="50b73-199">NOME</span><span class="sxs-lookup"><span data-stu-id="50b73-199">Name</span></span>|<span data-ttu-id="50b73-200">String</span><span class="sxs-lookup"><span data-stu-id="50b73-200">String</span></span>|<span data-ttu-id="50b73-201">Sì</span><span class="sxs-lookup"><span data-stu-id="50b73-201">Yes</span></span>|<span data-ttu-id="50b73-202">n/d</span><span class="sxs-lookup"><span data-stu-id="50b73-202">n/a</span></span>|<span data-ttu-id="50b73-203">Nome/identificatore della funzione</span><span class="sxs-lookup"><span data-stu-id="50b73-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="50b73-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="50b73-204">ReturnType</span></span>|<span data-ttu-id="50b73-205">String</span><span class="sxs-lookup"><span data-stu-id="50b73-205">String</span></span>|<span data-ttu-id="50b73-206">No</span><span class="sxs-lookup"><span data-stu-id="50b73-206">No</span></span>|<span data-ttu-id="50b73-207">Void</span><span class="sxs-lookup"><span data-stu-id="50b73-207">Void</span></span>|<span data-ttu-id="50b73-208">Il tipo restituito EDM della funzione</span><span class="sxs-lookup"><span data-stu-id="50b73-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="50b73-209">Aggregate</span><span class="sxs-lookup"><span data-stu-id="50b73-209">Aggregate</span></span>|<span data-ttu-id="50b73-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="50b73-210">Boolean</span></span>|<span data-ttu-id="50b73-211">No</span><span class="sxs-lookup"><span data-stu-id="50b73-211">No</span></span>|<span data-ttu-id="50b73-212">False</span><span class="sxs-lookup"><span data-stu-id="50b73-212">False</span></span>|<span data-ttu-id="50b73-213">Restituisce True se si tratta di una funzione di aggregazione</span><span class="sxs-lookup"><span data-stu-id="50b73-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="50b73-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="50b73-214">BuiltIn</span></span>|<span data-ttu-id="50b73-215">Boolean</span><span class="sxs-lookup"><span data-stu-id="50b73-215">Boolean</span></span>|<span data-ttu-id="50b73-216">No</span><span class="sxs-lookup"><span data-stu-id="50b73-216">No</span></span>|<span data-ttu-id="50b73-217">True</span><span class="sxs-lookup"><span data-stu-id="50b73-217">True</span></span>|<span data-ttu-id="50b73-218">Restituisce True se la funzione è inclusa nell'archivio dati</span><span class="sxs-lookup"><span data-stu-id="50b73-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="50b73-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="50b73-219">StoreFunctionName</span></span>|<span data-ttu-id="50b73-220">String</span><span class="sxs-lookup"><span data-stu-id="50b73-220">String</span></span>|<span data-ttu-id="50b73-221">No</span><span class="sxs-lookup"><span data-stu-id="50b73-221">No</span></span>|<span data-ttu-id="50b73-222">\<Nome ></span><span class="sxs-lookup"><span data-stu-id="50b73-222">\<Name></span></span>|<span data-ttu-id="50b73-223">Nome della funzione nell'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="50b73-223">Function Name in the data store.</span></span>  <span data-ttu-id="50b73-224">Consente di eseguire un determinato tipo di reindirizzamento dei nomi delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="50b73-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="50b73-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="50b73-225">NiladicFunction</span></span>|<span data-ttu-id="50b73-226">Boolean</span><span class="sxs-lookup"><span data-stu-id="50b73-226">Boolean</span></span>|<span data-ttu-id="50b73-227">No</span><span class="sxs-lookup"><span data-stu-id="50b73-227">No</span></span>|<span data-ttu-id="50b73-228">False</span><span class="sxs-lookup"><span data-stu-id="50b73-228">False</span></span>|<span data-ttu-id="50b73-229">Restituisce True se la funzione non richiede parametri e viene chiamata senza parametri</span><span class="sxs-lookup"><span data-stu-id="50b73-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="50b73-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="50b73-230">ParameterType</span></span><br /><br /> <span data-ttu-id="50b73-231">Semantics</span><span class="sxs-lookup"><span data-stu-id="50b73-231">Semantics</span></span>|<span data-ttu-id="50b73-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="50b73-232">ParameterSemantics</span></span>|<span data-ttu-id="50b73-233">No</span><span class="sxs-lookup"><span data-stu-id="50b73-233">No</span></span>|<span data-ttu-id="50b73-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="50b73-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="50b73-235">Conversione</span><span class="sxs-lookup"><span data-stu-id="50b73-235">Conversion</span></span>|<span data-ttu-id="50b73-236">Scelta della modalità con cui la pipeline della query gestisce la sostituzione del tipo di parametro:</span><span class="sxs-lookup"><span data-stu-id="50b73-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="50b73-237">- ExactMatchOnly</span><span class="sxs-lookup"><span data-stu-id="50b73-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="50b73-238">- AllowImplicitPromotion</span><span class="sxs-lookup"><span data-stu-id="50b73-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="50b73-239">- AllowImplicitConversion</span><span class="sxs-lookup"><span data-stu-id="50b73-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="50b73-240">**Nodo parametri**</span><span class="sxs-lookup"><span data-stu-id="50b73-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="50b73-241">Ogni funzione presenta una raccolta di uno o più nodi Parameter.</span><span class="sxs-lookup"><span data-stu-id="50b73-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="50b73-242">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="50b73-242">Attribute Name</span></span>|<span data-ttu-id="50b73-243">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="50b73-243">Data Type</span></span>|<span data-ttu-id="50b73-244">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="50b73-244">Required</span></span>|<span data-ttu-id="50b73-245">Default Value</span><span class="sxs-lookup"><span data-stu-id="50b73-245">Default Value</span></span>|<span data-ttu-id="50b73-246">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50b73-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="50b73-247">NOME</span><span class="sxs-lookup"><span data-stu-id="50b73-247">Name</span></span>|<span data-ttu-id="50b73-248">String</span><span class="sxs-lookup"><span data-stu-id="50b73-248">String</span></span>|<span data-ttu-id="50b73-249">Sì</span><span class="sxs-lookup"><span data-stu-id="50b73-249">Yes</span></span>|<span data-ttu-id="50b73-250">n/d</span><span class="sxs-lookup"><span data-stu-id="50b73-250">n/a</span></span>|<span data-ttu-id="50b73-251">Nome/identificatore del parametro.</span><span class="sxs-lookup"><span data-stu-id="50b73-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="50b73-252">Type</span><span class="sxs-lookup"><span data-stu-id="50b73-252">Type</span></span>|<span data-ttu-id="50b73-253">String</span><span class="sxs-lookup"><span data-stu-id="50b73-253">String</span></span>|<span data-ttu-id="50b73-254">Yes</span><span class="sxs-lookup"><span data-stu-id="50b73-254">Yes</span></span>|<span data-ttu-id="50b73-255">n/d</span><span class="sxs-lookup"><span data-stu-id="50b73-255">n/a</span></span>|<span data-ttu-id="50b73-256">Tipo EDM del parametro.</span><span class="sxs-lookup"><span data-stu-id="50b73-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="50b73-257">Modalità</span><span class="sxs-lookup"><span data-stu-id="50b73-257">Mode</span></span>|<span data-ttu-id="50b73-258">Parametro</span><span class="sxs-lookup"><span data-stu-id="50b73-258">Parameter</span></span><br /><br /> <span data-ttu-id="50b73-259">Direction</span><span class="sxs-lookup"><span data-stu-id="50b73-259">Direction</span></span>|<span data-ttu-id="50b73-260">Yes</span><span class="sxs-lookup"><span data-stu-id="50b73-260">Yes</span></span>|<span data-ttu-id="50b73-261">n/d</span><span class="sxs-lookup"><span data-stu-id="50b73-261">n/a</span></span>|<span data-ttu-id="50b73-262">Direzione del parametro:</span><span class="sxs-lookup"><span data-stu-id="50b73-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="50b73-263">-   in</span><span class="sxs-lookup"><span data-stu-id="50b73-263">-   in</span></span><br /><span data-ttu-id="50b73-264">-out</span><span class="sxs-lookup"><span data-stu-id="50b73-264">-   out</span></span><br /><span data-ttu-id="50b73-265">-Inout</span><span class="sxs-lookup"><span data-stu-id="50b73-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="50b73-266">Attributo namespace</span><span class="sxs-lookup"><span data-stu-id="50b73-266">Namespace Attribute</span></span>  
 <span data-ttu-id="50b73-267">Ogni provider dell'archivio dati deve definire uno spazio dei nomi o un gruppo di spazi dei nomi per le informazioni definite nel manifesto.</span><span class="sxs-lookup"><span data-stu-id="50b73-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="50b73-268">Tale spazio dei nomi può essere usato nelle query Entity SQL per risolvere nomi di funzioni e tipi.</span><span class="sxs-lookup"><span data-stu-id="50b73-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="50b73-269">Ad esempio: SqlServer.</span><span class="sxs-lookup"><span data-stu-id="50b73-269">For instance: SqlServer.</span></span> <span data-ttu-id="50b73-270">Lo spazio dei nomi deve essere diverso dallo spazio dei nomi canonico, ovvero EDM, definito dai servizi di entità per funzioni standard che devono essere supportate dalle query Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="50b73-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b73-271">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50b73-271">See also</span></span>

- [<span data-ttu-id="50b73-272">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="50b73-272">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
