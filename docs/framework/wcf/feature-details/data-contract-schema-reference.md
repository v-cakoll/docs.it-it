---
title: Riferimento allo schema del contratto dati
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: 04d1f753e5788460404942a21a29e1612f674e90
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593568"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="5696f-102">Riferimento allo schema del contratto dati</span><span class="sxs-lookup"><span data-stu-id="5696f-102">Data Contract Schema Reference</span></span>

<span data-ttu-id="5696f-103">In questo argomento viene descritto il sottoinsieme dell'XML Schema (XSD) utilizzato da <xref:System.Runtime.Serialization.DataContractSerializer> per descrivere i tipi di Common Language Runtime (CLR) per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="5696f-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>

## <a name="datacontractserializer-mappings"></a><span data-ttu-id="5696f-104">Mapping DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="5696f-104">DataContractSerializer Mappings</span></span>

<span data-ttu-id="5696f-105">`DataContractSerializer`Esegue il mapping dei tipi CLR a XSD quando i metadati vengono esportati da un servizio Windows Communication Foundation (WCF) utilizzando un endpoint di metadati o lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5696f-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="5696f-106">Per ulteriori informazioni, vedere [Data Contract Serializer](data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="5696f-106">For more information, see [Data Contract Serializer](data-contract-serializer.md).</span></span>

<span data-ttu-id="5696f-107">`DataContractSerializer` esegue, inoltre, il mapping di XSD ai tipi CLR quando viene utilizzato Svcutil.exe per accedere a documenti WSDL (Web Services Description Language) o XSD e generare contratti dati per servizi o client.</span><span class="sxs-lookup"><span data-stu-id="5696f-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>

<span data-ttu-id="5696f-108">È possibile eseguire il mapping ai tipi CLR tramite `DataContractSerializer`solo delle istanze dell'XML Schema conformi ai requisiti indicati nel presente documento.</span><span class="sxs-lookup"><span data-stu-id="5696f-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>

### <a name="support-levels"></a><span data-ttu-id="5696f-109">Livelli di supporto</span><span class="sxs-lookup"><span data-stu-id="5696f-109">Support Levels</span></span>

<span data-ttu-id="5696f-110">`DataContractSerializer` fornisce i livelli di supporto seguenti per una determinata funzionalità dell'XML Schema:</span><span class="sxs-lookup"><span data-stu-id="5696f-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>

- <span data-ttu-id="5696f-111">**Supportato**.</span><span class="sxs-lookup"><span data-stu-id="5696f-111">**Supported**.</span></span> <span data-ttu-id="5696f-112">È disponibile il mapping esplicito da questa funzionalità a tipi e/o attributi CLR mediante `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="5696f-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>

- <span data-ttu-id="5696f-113">**Ignorato**.</span><span class="sxs-lookup"><span data-stu-id="5696f-113">**Ignored**.</span></span> <span data-ttu-id="5696f-114">La funzionalità è consentita negli schemi importati da `DataContractSerializer`, ma non ha alcun effetto sulla generazione di codice.</span><span class="sxs-lookup"><span data-stu-id="5696f-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>

- <span data-ttu-id="5696f-115">Non **consentito**.</span><span class="sxs-lookup"><span data-stu-id="5696f-115">**Forbidden**.</span></span> <span data-ttu-id="5696f-116">`DataContractSerializer` non supporta l'importazione di uno schema mediante la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5696f-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="5696f-117">Svcutil.exe, ad esempio, quando si accede a un documento WSDL con uno schema che utilizza tale funzionalità, torna a utilizzare <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="5696f-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="5696f-118">Questo accade per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5696f-118">This is by default.</span></span>

## <a name="general-information"></a><span data-ttu-id="5696f-119">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="5696f-119">General Information</span></span>

- <span data-ttu-id="5696f-120">Lo spazio dei nomi dello schema viene descritto nella pagina relativa a [XML Schema](https://www.w3.org/2001/XMLSchema).</span><span class="sxs-lookup"><span data-stu-id="5696f-120">The schema namespace is described at [XML Schema](https://www.w3.org/2001/XMLSchema).</span></span> <span data-ttu-id="5696f-121">In questo documento viene utilizzato il prefisso "xs".</span><span class="sxs-lookup"><span data-stu-id="5696f-121">The prefix "xs" is used in this document.</span></span>

- <span data-ttu-id="5696f-122">Tutti gli attributi con un spazio dei nomi non di schema vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="5696f-122">Any attributes with a non-schema namespace are ignored.</span></span>

- <span data-ttu-id="5696f-123">Tutte le annotazioni, ad eccezione di quelle descritte in questo documento, vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="5696f-123">Any annotations (except for those described in this document) are ignored.</span></span>

### <a name="xsschema-attributes"></a><span data-ttu-id="5696f-124">\<xs:schema>: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-124">\<xs:schema>: attributes</span></span>

|<span data-ttu-id="5696f-125">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-125">Attribute</span></span>|<span data-ttu-id="5696f-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="5696f-126">DataContract</span></span>|
|---------------|------------------|
|`attributeFormDefault`|<span data-ttu-id="5696f-127">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-127">Ignored.</span></span>|
|`blockDefault`|<span data-ttu-id="5696f-128">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-128">Ignored.</span></span>|
|`elementFormDefault`|<span data-ttu-id="5696f-129">Deve essere qualificato.</span><span class="sxs-lookup"><span data-stu-id="5696f-129">Must be qualified.</span></span> <span data-ttu-id="5696f-130">Per essere supportati da `DataContractSerializer`, tutti gli elementi devono essere qualificati per uno schema.</span><span class="sxs-lookup"><span data-stu-id="5696f-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="5696f-131">Questa operazione può essere eseguita impostando su xs:schema/@elementFormDefault "qualified" o impostando su xs:element/@form "qualified" per ogni singola dichiarazione di elemento.</span><span class="sxs-lookup"><span data-stu-id="5696f-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|
|`finalDefault`|<span data-ttu-id="5696f-132">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-132">Ignored.</span></span>|
|`Id`|<span data-ttu-id="5696f-133">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-133">Ignored.</span></span>|
|`targetNamespace`|<span data-ttu-id="5696f-134">Supportato e associato allo spazio dei nomi del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="5696f-135">Se questo attributo non viene specificato, viene utilizzato lo spazio dei nomi vuoto,</span><span class="sxs-lookup"><span data-stu-id="5696f-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="5696f-136">Non può essere lo spazio dei nomi riservato `http://schemas.microsoft.com/2003/10/Serialization/` .</span><span class="sxs-lookup"><span data-stu-id="5696f-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|
|`version`|<span data-ttu-id="5696f-137">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-137">Ignored.</span></span>|

### <a name="xsschema-contents"></a><span data-ttu-id="5696f-138">\<xs:schema>: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-138">\<xs:schema>: contents</span></span>

|<span data-ttu-id="5696f-139">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-139">Contents</span></span>|<span data-ttu-id="5696f-140">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-140">Schema</span></span>|
|--------------|------------|
|`include`|<span data-ttu-id="5696f-141">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-141">Supported.</span></span> <span data-ttu-id="5696f-142">`DataContractSerializer` supporta xs:include e xs:import.</span><span class="sxs-lookup"><span data-stu-id="5696f-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="5696f-143">Tuttavia, Svcutil.exe restringe i seguenti riferimenti `xs:include/@schemaLocation` e `xs:import/@location` quando i metadati vengono caricati da un file locale.</span><span class="sxs-lookup"><span data-stu-id="5696f-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="5696f-144">In questo caso, l'elenco dei file di schema deve essere passato tramite un meccanismo fuori banda e non tramite `include` ; i documenti dello schema `include`vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="5696f-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`redefine`|<span data-ttu-id="5696f-145">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-145">Forbidden.</span></span> <span data-ttu-id="5696f-146">L'utilizzo di `xs:redefine` non è consentito da `DataContractSerializer` per motivi di sicurezza: `x:redefine` rende necessario seguire `schemaLocation` .</span><span class="sxs-lookup"><span data-stu-id="5696f-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="5696f-147">In alcune circostanze, Svcutil.exe che utilizza DataContract restringe l'utilizzo di `schemaLocation`.</span><span class="sxs-lookup"><span data-stu-id="5696f-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|
|`import`|<span data-ttu-id="5696f-148">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-148">Supported.</span></span> <span data-ttu-id="5696f-149">`DataContractSerializer` supporta `xs:include` e `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="5696f-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="5696f-150">Tuttavia, Svcutil.exe restringe i seguenti riferimenti `xs:include/@schemaLocation` e `xs:import/@location` quando i metadati vengono caricati da un file locale.</span><span class="sxs-lookup"><span data-stu-id="5696f-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="5696f-151">In questo caso, l'elenco dei file di schema deve essere passato tramite un meccanismo fuori banda e non tramite `include` ; i documenti dello schema `include`vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="5696f-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`simpleType`|<span data-ttu-id="5696f-152">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-152">Supported.</span></span> <span data-ttu-id="5696f-153">Vedere la sezione `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="5696f-153">See the `xs:simpleType` section.</span></span>|
|`complexType`|<span data-ttu-id="5696f-154">Supportato, esegue il mapping ai contratti dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="5696f-155">Vedere la sezione `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="5696f-155">See the `xs:complexType` section.</span></span>|
|`group`|<span data-ttu-id="5696f-156">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-156">Ignored.</span></span> <span data-ttu-id="5696f-157">`DataContractSerializer` non supporta l'utilizzo di `xs:group`, `xs:attributeGroup`e `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5696f-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5696f-158">Queste dichiarazioni vengono ignorate come elementi figlio di `xs:schema`, ma non è possibile fare riferimento a esse da `complexType` o da altri costrutti supportati.</span><span class="sxs-lookup"><span data-stu-id="5696f-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`attributeGroup`|<span data-ttu-id="5696f-159">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-159">Ignored.</span></span> <span data-ttu-id="5696f-160">`DataContractSerializer` non supporta l'utilizzo di `xs:group`, `xs:attributeGroup`e `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5696f-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5696f-161">Queste dichiarazioni vengono ignorate come elementi figlio di `xs:schema`, ma non è possibile fare riferimento a esse da `complexType` o da altri costrutti supportati.</span><span class="sxs-lookup"><span data-stu-id="5696f-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`element`|<span data-ttu-id="5696f-162">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-162">Supported.</span></span> <span data-ttu-id="5696f-163">Vedere Dichiarazione di elemento globale (GED, Global Element Declaration).</span><span class="sxs-lookup"><span data-stu-id="5696f-163">See Global Element Declaration (GED).</span></span>|
|`attribute`|<span data-ttu-id="5696f-164">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-164">Ignored.</span></span> <span data-ttu-id="5696f-165">`DataContractSerializer` non supporta l'utilizzo di `xs:group`, `xs:attributeGroup`e `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5696f-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5696f-166">Queste dichiarazioni vengono ignorate come elementi figlio di `xs:schema`, ma non è possibile fare riferimento a esse da `complexType` o da altri costrutti supportati.</span><span class="sxs-lookup"><span data-stu-id="5696f-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`notation`|<span data-ttu-id="5696f-167">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-167">Ignored.</span></span>|

## <a name="complex-types--xscomplextype"></a><span data-ttu-id="5696f-168">Tipi complessi:\<xs:complexType></span><span class="sxs-lookup"><span data-stu-id="5696f-168">Complex Types – \<xs:complexType></span></span>

### <a name="general-information"></a><span data-ttu-id="5696f-169">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="5696f-169">General Information</span></span>

<span data-ttu-id="5696f-170">Ogni tipo complesso \<xs:complexType> esegue il mapping a un contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>

### <a name="xscomplextype-attributes"></a><span data-ttu-id="5696f-171">\<xs:complexType>: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-171">\<xs:complexType>: attributes</span></span>

|<span data-ttu-id="5696f-172">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-172">Attribute</span></span>|<span data-ttu-id="5696f-173">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-173">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="5696f-174">Deve essere false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5696f-174">Must be false (default).</span></span>|
|`block`|<span data-ttu-id="5696f-175">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-175">Forbidden.</span></span>|
|`final`|<span data-ttu-id="5696f-176">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-176">Ignored.</span></span>|
|`id`|<span data-ttu-id="5696f-177">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-177">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="5696f-178">Deve essere false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5696f-178">Must be false (default).</span></span>|
|`name`|<span data-ttu-id="5696f-179">Supportato e associato al nome del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="5696f-180">Se nel nome sono presenti punti, viene effettuato il tentativo di eseguire il mapping del tipo a un tipo interno.</span><span class="sxs-lookup"><span data-stu-id="5696f-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="5696f-181">Ad esempio, un tipo complesso denominato `A.B` esegue il mapping a un tipo di contratto dati che è un tipo interno di un tipo con il nome di contratto dati `A`, ma solo se tale tipo di contratto dati esiste.</span><span class="sxs-lookup"><span data-stu-id="5696f-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="5696f-182">Possono esistere più livelli di annidamento: ad esempio, `A.B.C` può essere un tipo interno, ma solo se esistono sia `A` che `A.B` .</span><span class="sxs-lookup"><span data-stu-id="5696f-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|

### <a name="xscomplextype-contents"></a><span data-ttu-id="5696f-183">\<xs:complexType>: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-183">\<xs:complexType>: contents</span></span>

|<span data-ttu-id="5696f-184">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-184">Contents</span></span>|<span data-ttu-id="5696f-185">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-185">Schema</span></span>|
|--------------|------------|
|`simpleContent`|<span data-ttu-id="5696f-186">Non sono consentite estensioni.</span><span class="sxs-lookup"><span data-stu-id="5696f-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="5696f-187">Sono consentite restrizioni solo da `anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="5696f-187">Restriction is allowed only from `anySimpleType`.</span></span>|
|`complexContent`|<span data-ttu-id="5696f-188">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-188">Supported.</span></span> <span data-ttu-id="5696f-189">Vedere "Ereditarietà".</span><span class="sxs-lookup"><span data-stu-id="5696f-189">See "Inheritance".</span></span>|
|`group`|<span data-ttu-id="5696f-190">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-190">Forbidden.</span></span>|
|`all`|<span data-ttu-id="5696f-191">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-191">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="5696f-192">Accesso negato</span><span class="sxs-lookup"><span data-stu-id="5696f-192">Forbidden</span></span>|
|`sequence`|<span data-ttu-id="5696f-193">Supportato, esegue il mapping a membri dati di un contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-193">Supported, maps to data members of a data contract.</span></span>|
|`attribute`|<span data-ttu-id="5696f-194">Non consentito, anche se use = "prohibited" (con un'eccezione).</span><span class="sxs-lookup"><span data-stu-id="5696f-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="5696f-195">Sono supportati solo attributi facoltativi dello spazio dei nomi dello schema di serializzazione standard.</span><span class="sxs-lookup"><span data-stu-id="5696f-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="5696f-196">Essi non eseguono il mapping ai membri dati nel modello di programmazione del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="5696f-197">Attualmente, solo uno di tali attributi ha significato e viene illustrato nella sezione ISerializable.</span><span class="sxs-lookup"><span data-stu-id="5696f-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="5696f-198">Tutti gli altri vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="5696f-198">All others are ignored.</span></span>|
|`attributeGroup`|<span data-ttu-id="5696f-199">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-199">Forbidden.</span></span> <span data-ttu-id="5696f-200">Nella versione di WCF V1 `DataContractSerializer` Ignora la presenza di `attributeGroup` all'interno di `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="5696f-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|
|`anyAttribute`|<span data-ttu-id="5696f-201">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-201">Forbidden.</span></span>|
|<span data-ttu-id="5696f-202">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="5696f-202">(empty)</span></span>|<span data-ttu-id="5696f-203">Esegue il mapping a un contratto dati senza membri dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-203">Maps to a data contract with no data members.</span></span>|

### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="5696f-204">\<xs:sequence>in un tipo complesso: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-204">\<xs:sequence> in a complex type: attributes</span></span>

|<span data-ttu-id="5696f-205">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-205">Attribute</span></span>|<span data-ttu-id="5696f-206">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-206">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="5696f-207">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-207">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="5696f-208">Deve essere 1 (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5696f-208">Must be 1 (default).</span></span>|
|`minOccurs`|<span data-ttu-id="5696f-209">Deve essere 1 (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5696f-209">Must be 1 (default).</span></span>|

### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="5696f-210">\<xs:sequence>in un tipo complesso: Contents</span><span class="sxs-lookup"><span data-stu-id="5696f-210">\<xs:sequence> in a complex type: contents</span></span>

|<span data-ttu-id="5696f-211">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-211">Contents</span></span>|<span data-ttu-id="5696f-212">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-212">Schema</span></span>|
|--------------|------------|
|`element`|<span data-ttu-id="5696f-213">Ogni istanza esegue il mapping a un membro dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-213">Each instance maps to a data member.</span></span>|
|`group`|<span data-ttu-id="5696f-214">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-214">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="5696f-215">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-215">Forbidden.</span></span>|
|`sequence`|<span data-ttu-id="5696f-216">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-216">Forbidden.</span></span>|
|`any`|<span data-ttu-id="5696f-217">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-217">Forbidden.</span></span>|
|<span data-ttu-id="5696f-218">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="5696f-218">(empty)</span></span>|<span data-ttu-id="5696f-219">Esegue il mapping a un contratto dati senza membri dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-219">Maps to a data contract with no data members.</span></span>|

## <a name="elements--xselement"></a><span data-ttu-id="5696f-220">Elementi\<xs:element></span><span class="sxs-lookup"><span data-stu-id="5696f-220">Elements – \<xs:element></span></span>

### <a name="general-information"></a><span data-ttu-id="5696f-221">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="5696f-221">General Information</span></span>

<span data-ttu-id="5696f-222">`<xs:element>` può verificarsi nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5696f-222">`<xs:element>` can occur in the following contexts:</span></span>

- <span data-ttu-id="5696f-223">Può verificarsi all'interno di un tag `<xs:sequence>`che descrive un membro dati di un contratto dati regolare (non di raccolta).</span><span class="sxs-lookup"><span data-stu-id="5696f-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="5696f-224">In questo caso, l'attributo `maxOccurs` deve essere 1.</span><span class="sxs-lookup"><span data-stu-id="5696f-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="5696f-225">Il valore 0 non è consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-225">(A value of 0 is not allowed).</span></span>

- <span data-ttu-id="5696f-226">Può verificarsi all'interno di un tag `<xs:sequence>`che descrive un membro dati di un contratto dati di raccolta.</span><span class="sxs-lookup"><span data-stu-id="5696f-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="5696f-227">In questo caso, l'attributo `maxOccurs` deve essere maggiore di 1 o "unbounded".</span><span class="sxs-lookup"><span data-stu-id="5696f-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>

- <span data-ttu-id="5696f-228">Può verificarsi all'interno di un `<xs:schema>` come dichiarazione di elemento globale (GED).</span><span class="sxs-lookup"><span data-stu-id="5696f-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="5696f-229">\<xs:element>con maxOccurs = 1 all'interno di un \<xs:sequence> (membri dati)</span><span class="sxs-lookup"><span data-stu-id="5696f-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>

|<span data-ttu-id="5696f-230">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-230">Attribute</span></span>|<span data-ttu-id="5696f-231">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-231">Schema</span></span>|
|---------------|------------|
|`ref`|<span data-ttu-id="5696f-232">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-232">Forbidden.</span></span>|
|`name`|<span data-ttu-id="5696f-233">Supportato, esegue il mapping al nome del membro dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-233">Supported, maps to the data member name.</span></span>|
|`type`|<span data-ttu-id="5696f-234">Supportato, esegue il mapping al tipo del membro dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="5696f-235">Per ulteriori informazioni, vedere Mapping di tipi/primitivi.</span><span class="sxs-lookup"><span data-stu-id="5696f-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="5696f-236">Se non è specificato (e se l'elemento non contiene un tipo anonimo), viene presupposto `xs:anyType` .</span><span class="sxs-lookup"><span data-stu-id="5696f-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|
|`block`|<span data-ttu-id="5696f-237">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-237">Ignored.</span></span>|
|`default`|<span data-ttu-id="5696f-238">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-238">Forbidden.</span></span>|
|`fixed`|<span data-ttu-id="5696f-239">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-239">Forbidden.</span></span>|
|`form`|<span data-ttu-id="5696f-240">Deve essere qualificato.</span><span class="sxs-lookup"><span data-stu-id="5696f-240">Must be qualified.</span></span> <span data-ttu-id="5696f-241">Questo attributo può essere impostato tramite `elementFormDefault` su `xs:schema`.</span><span class="sxs-lookup"><span data-stu-id="5696f-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|
|`id`|<span data-ttu-id="5696f-242">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-242">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="5696f-243">1</span><span class="sxs-lookup"><span data-stu-id="5696f-243">1</span></span>|
|`minOccurs`|<span data-ttu-id="5696f-244">Esegue il mapping alla proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> di un membro dati (`IsRequired` è true quando `minOccurs` è 1).</span><span class="sxs-lookup"><span data-stu-id="5696f-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|
|`nillable`|<span data-ttu-id="5696f-245">Influenza il mapping dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5696f-245">Affects type mapping.</span></span> <span data-ttu-id="5696f-246">Vedere Mapping di tipi/primitivi.</span><span class="sxs-lookup"><span data-stu-id="5696f-246">See Type/primitive mapping.</span></span>|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="5696f-247">\<xs:element>con maxOccurs>1 all'interno di un \<xs:sequence> (raccolte)</span><span class="sxs-lookup"><span data-stu-id="5696f-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>

- <span data-ttu-id="5696f-248">Esegue il mapping a un <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5696f-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>

- <span data-ttu-id="5696f-249">Nei tipi di raccolta, è consentito un solo xs:element all'interno di un xs:sequence.</span><span class="sxs-lookup"><span data-stu-id="5696f-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>

 <span data-ttu-id="5696f-250">Le raccolte possono essere dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5696f-250">Collections can be of the following types:</span></span>

- <span data-ttu-id="5696f-251">Raccolte regolari (ad esempio, matrici).</span><span class="sxs-lookup"><span data-stu-id="5696f-251">Regular collections (for example, arrays).</span></span>

- <span data-ttu-id="5696f-252">Raccolte dizionario (esecuzione del mapping di un valore all'altro; ad esempio, <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="5696f-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>

- <span data-ttu-id="5696f-253">La sola differenza tra un dizionario e una matrice di un tipo di coppia chiave/valore è nel modello di programmazione generato.</span><span class="sxs-lookup"><span data-stu-id="5696f-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="5696f-254">Esiste un meccanismo di annotazione di schema che può essere utilizzato per indicare che un determinato tipo è una raccolta dizionario.</span><span class="sxs-lookup"><span data-stu-id="5696f-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>

<span data-ttu-id="5696f-255">Le regole per gli attributi `ref`, `block`, `default`, `fixed`, `form`e `id` solo uguali a quelle valide per il caso non di raccolta.</span><span class="sxs-lookup"><span data-stu-id="5696f-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="5696f-256">Tra gli altri attributi sono inclusi quelli riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5696f-256">Other attributes include those in the following table.</span></span>

|<span data-ttu-id="5696f-257">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-257">Attribute</span></span>|<span data-ttu-id="5696f-258">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-258">Schema</span></span>|
|---------------|------------|
|`name`|<span data-ttu-id="5696f-259">Supportato, esegue il mapping alla proprietà <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> nell'attributo `CollectionDataContractAttribute` .</span><span class="sxs-lookup"><span data-stu-id="5696f-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|
|`type`|<span data-ttu-id="5696f-260">Supportato, esegue il mapping al tipo memorizzato nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="5696f-260">Supported, maps to the type stored in the collection.</span></span>|
|`maxOccurs`|<span data-ttu-id="5696f-261">Maggiore di 1 o "unbounded".</span><span class="sxs-lookup"><span data-stu-id="5696f-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="5696f-262">Lo schema DC deve utilizzare "unbounded".</span><span class="sxs-lookup"><span data-stu-id="5696f-262">The DC schema should use "unbounded".</span></span>|
|`minOccurs`|<span data-ttu-id="5696f-263">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-263">Ignored.</span></span>|
|`nillable`|<span data-ttu-id="5696f-264">Influenza il mapping dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5696f-264">Affects type mapping.</span></span> <span data-ttu-id="5696f-265">Questo attributo viene ignorato per le raccolte dizionario.</span><span class="sxs-lookup"><span data-stu-id="5696f-265">This attribute is ignored for dictionary collections.</span></span>|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="5696f-266">\<xs:element>all'interno di una \<xs:schema> dichiarazione di elemento globale</span><span class="sxs-lookup"><span data-stu-id="5696f-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>

- <span data-ttu-id="5696f-267">Una dichiarazione di elemento globale (GED) con lo stesso nome e lo stesso spazio dei nomi di un tipo nello schema, o che definisce un tipo anonimo al suo interno, viene definita come associata al tipo.</span><span class="sxs-lookup"><span data-stu-id="5696f-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>

- <span data-ttu-id="5696f-268">Esportazione dello schema: vengono generate dichiarazioni di elementi globali associate per ogni tipo generato, sia semplice che complesso.</span><span class="sxs-lookup"><span data-stu-id="5696f-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>

- <span data-ttu-id="5696f-269">Deserializzazione/serializzazione: vengono utilizzate dichiarazioni di elementi globali associate come elementi radice per il tipo.</span><span class="sxs-lookup"><span data-stu-id="5696f-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>

- <span data-ttu-id="5696f-270">Importazione dello schema: le dichiarazioni di elementi globali associate non sono necessarie e vengono ignorate se seguono le regole seguenti (a meno che non definiscano tipi).</span><span class="sxs-lookup"><span data-stu-id="5696f-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>

|<span data-ttu-id="5696f-271">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-271">Attribute</span></span>|<span data-ttu-id="5696f-272">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-272">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="5696f-273">Deve essere false per le dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-273">Must be false for associated GEDs.</span></span>|
|`block`|<span data-ttu-id="5696f-274">Non consentito nelle dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-274">Forbidden in associated GEDs.</span></span>|
|`default`|<span data-ttu-id="5696f-275">Non consentito nelle dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-275">Forbidden in associated GEDs.</span></span>|
|`final`|<span data-ttu-id="5696f-276">Deve essere false per le dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-276">Must be false for associated GEDs.</span></span>|
|`fixed`|<span data-ttu-id="5696f-277">Non consentito nelle dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-277">Forbidden in associated GEDs.</span></span>|
|`id`|<span data-ttu-id="5696f-278">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-278">Ignored.</span></span>|
|`name`|<span data-ttu-id="5696f-279">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-279">Supported.</span></span> <span data-ttu-id="5696f-280">Vedere la definizione di dichiarazione di elemento globale associata.</span><span class="sxs-lookup"><span data-stu-id="5696f-280">See the definition of associated GEDs.</span></span>|
|`nillable`|<span data-ttu-id="5696f-281">Deve essere true per le dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-281">Must be true for associated GEDs.</span></span>|
|`substitutionGroup`|<span data-ttu-id="5696f-282">Non consentito nelle dichiarazioni di elementi globali associate.</span><span class="sxs-lookup"><span data-stu-id="5696f-282">Forbidden in associated GEDs.</span></span>|
|`type`|<span data-ttu-id="5696f-283">Supportato e deve corrispondere al tipo associato per le dichiarazioni di elementi globali associate (a meno che l'elemento non contenga un tipo anonimo).</span><span class="sxs-lookup"><span data-stu-id="5696f-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|

### <a name="xselement-contents"></a><span data-ttu-id="5696f-284">\<xs:element>: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-284">\<xs:element>: contents</span></span>

|<span data-ttu-id="5696f-285">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-285">Contents</span></span>|<span data-ttu-id="5696f-286">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-286">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5696f-287">Supportato.\*</span><span class="sxs-lookup"><span data-stu-id="5696f-287">Supported.\*</span></span>|
|`complexType`|<span data-ttu-id="5696f-288">Supportato.\*</span><span class="sxs-lookup"><span data-stu-id="5696f-288">Supported.\*</span></span>|
|`unique`|<span data-ttu-id="5696f-289">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-289">Ignored.</span></span>|
|`key`|<span data-ttu-id="5696f-290">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-290">Ignored.</span></span>|
|`keyref`|<span data-ttu-id="5696f-291">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-291">Ignored.</span></span>|
|<span data-ttu-id="5696f-292">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="5696f-292">(blank)</span></span>|<span data-ttu-id="5696f-293">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-293">Supported.</span></span>|

<span data-ttu-id="5696f-294">\*Quando si usa `simpleType` il `complexType,` mapping di e per i tipi anonimi è uguale a quello per i tipi non anonimi, ad eccezione del fatto che non sono presenti contratti dati anonimi e quindi viene creato un contratto dati denominato, con un nome generato derivato dal nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="5696f-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="5696f-295">Le regole per i tipi anonimi sono riportate nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="5696f-295">The rules for anonymous types are in the following list:</span></span>

- <span data-ttu-id="5696f-296">Dettagli di implementazione WCF: se il `xs:element` nome non contiene punti, il tipo anonimo esegue il mapping a un tipo interno del tipo di contratto dati esterno.</span><span class="sxs-lookup"><span data-stu-id="5696f-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="5696f-297">Se il nome contiene punti, il tipo di contratto dati risultante è indipendente (non è un tipo interno).</span><span class="sxs-lookup"><span data-stu-id="5696f-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>

- <span data-ttu-id="5696f-298">Il nome del contratto dati generato del tipo interno è il nome del contratto dati del tipo esterno seguito da un punto, dal nome dell'elemento e dalla stringa "Type".</span><span class="sxs-lookup"><span data-stu-id="5696f-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>

- <span data-ttu-id="5696f-299">Se esiste già un contratto dati con tale nome, il nome viene reso univoco aggiungendo "1", "2", "3" e così via, fino a creare un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="5696f-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>

## <a name="simple-types---xssimpletype"></a><span data-ttu-id="5696f-300">Tipi semplici-\<xs:simpleType></span><span class="sxs-lookup"><span data-stu-id="5696f-300">Simple Types - \<xs:simpleType></span></span>

### <a name="xssimpletype-attributes"></a><span data-ttu-id="5696f-301">\<xs:simpleType>: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-301">\<xs:simpleType>: attributes</span></span>

|<span data-ttu-id="5696f-302">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-302">Attribute</span></span>|<span data-ttu-id="5696f-303">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-303">Schema</span></span>|
|---------------|------------|
|`final`|<span data-ttu-id="5696f-304">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-304">Ignored.</span></span>|
|`id`|<span data-ttu-id="5696f-305">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-305">Ignored.</span></span>|
|`name`|<span data-ttu-id="5696f-306">Supportato, esegue il mapping al nome del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-306">Supported, maps to the data contract name.</span></span>|

### <a name="xssimpletype-contents"></a><span data-ttu-id="5696f-307">\<xs:simpleType>: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-307">\<xs:simpleType>: contents</span></span>

|<span data-ttu-id="5696f-308">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-308">Contents</span></span>|<span data-ttu-id="5696f-309">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-309">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="5696f-310">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-310">Supported.</span></span> <span data-ttu-id="5696f-311">Esegue il mapping a contratti dati di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5696f-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="5696f-312">Questo attributo viene ignorato se non corrisponde al modello di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5696f-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="5696f-313">Vedere la sezione sulle restrizioni `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="5696f-313">See the `xs:simpleType` restrictions section.</span></span>|
|`list`|<span data-ttu-id="5696f-314">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-314">Supported.</span></span> <span data-ttu-id="5696f-315">Esegue il mapping a contratti dati di enumerazione flag.</span><span class="sxs-lookup"><span data-stu-id="5696f-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="5696f-316">Vedere la sezione sugli elenchi `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="5696f-316">See the `xs:simpleType` lists section.</span></span>|
|`union`|<span data-ttu-id="5696f-317">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-317">Forbidden.</span></span>|

### \<xs:restriction>

- <span data-ttu-id="5696f-318">Le restrizioni di tipi complessi sono supportate solo per la base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="5696f-318">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>

- <span data-ttu-id="5696f-319">Le restrizioni di tipi semplici di `xs:string` che non hanno facet di restrizione diversi da `xs:enumeration` vengono associate a contratti dati di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5696f-319">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>

- <span data-ttu-id="5696f-320">Tutte le altre restrizioni di tipi semplici vengono associate ai tipi che limitano.</span><span class="sxs-lookup"><span data-stu-id="5696f-320">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="5696f-321">Ad esempio, una restrizione di `xs:int` esegue il mapping a un Integer, esattamente come fa `xs:int` .</span><span class="sxs-lookup"><span data-stu-id="5696f-321">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="5696f-322">Per ulteriori informazioni sul mapping dei tipi primitivi, vedere mapping di tipi/primitivi.</span><span class="sxs-lookup"><span data-stu-id="5696f-322">For more information about primitive type mapping, see Type/primitive mapping.</span></span>

### <a name="xsrestriction-attributes"></a><span data-ttu-id="5696f-323">\<xs:restriction>: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-323">\<xs:restriction>: attributes</span></span>

|<span data-ttu-id="5696f-324">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-324">Attribute</span></span>|<span data-ttu-id="5696f-325">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-325">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="5696f-326">Deve essere un tipo semplice supportato o `xs:anyType`.</span><span class="sxs-lookup"><span data-stu-id="5696f-326">Must be a supported simple type or `xs:anyType`.</span></span>|
|`id`|<span data-ttu-id="5696f-327">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-327">Ignored.</span></span>|

### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="5696f-328">\<xs:restriction>per tutti gli altri casi: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-328">\<xs:restriction> for all other cases: contents</span></span>

|<span data-ttu-id="5696f-329">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-329">Contents</span></span>|<span data-ttu-id="5696f-330">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-330">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5696f-331">Se presente, deve essere derivato da un tipo primitivo supportato.</span><span class="sxs-lookup"><span data-stu-id="5696f-331">If present, must be derived from a supported primitive type.</span></span>|
|`minExclusive`|<span data-ttu-id="5696f-332">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-332">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="5696f-333">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-333">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="5696f-334">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-334">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="5696f-335">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-335">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="5696f-336">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-336">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="5696f-337">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-337">Ignored.</span></span>|
|`length`|<span data-ttu-id="5696f-338">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-338">Ignored.</span></span>|
|`minLength`|<span data-ttu-id="5696f-339">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-339">Ignored.</span></span>|
|`maxLength`|<span data-ttu-id="5696f-340">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-340">Ignored.</span></span>|
|`enumeration`|<span data-ttu-id="5696f-341">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-341">Ignored.</span></span>|
|`whiteSpace`|<span data-ttu-id="5696f-342">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-342">Ignored.</span></span>|
|`pattern`|<span data-ttu-id="5696f-343">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-343">Ignored.</span></span>|
|<span data-ttu-id="5696f-344">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="5696f-344">(blank)</span></span>|<span data-ttu-id="5696f-345">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-345">Supported.</span></span>|

## <a name="enumeration"></a><span data-ttu-id="5696f-346">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="5696f-346">Enumeration</span></span>

### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="5696f-347">\<xs:restriction>per enumerazioni: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-347">\<xs:restriction> for enumerations: attributes</span></span>

|<span data-ttu-id="5696f-348">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-348">Attribute</span></span>|<span data-ttu-id="5696f-349">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-349">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="5696f-350">Se presente, deve essere `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="5696f-350">If present, must be `xs:string`.</span></span>|
|`id`|<span data-ttu-id="5696f-351">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-351">Ignored.</span></span>|

### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="5696f-352">\<xs:restriction>per enumerazioni: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-352">\<xs:restriction> for enumerations: contents</span></span>

|<span data-ttu-id="5696f-353">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-353">Contents</span></span>|<span data-ttu-id="5696f-354">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-354">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5696f-355">Se presente, deve essere una restrizione di enumerazione supportata dal contratto dati (questa sezione).</span><span class="sxs-lookup"><span data-stu-id="5696f-355">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|
|`minExclusive`|<span data-ttu-id="5696f-356">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-356">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="5696f-357">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-357">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="5696f-358">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-358">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="5696f-359">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-359">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="5696f-360">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-360">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="5696f-361">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-361">Ignored.</span></span>|
|`length`|<span data-ttu-id="5696f-362">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-362">Forbidden.</span></span>|
|`minLength`|<span data-ttu-id="5696f-363">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-363">Forbidden.</span></span>|
|`maxLength`|<span data-ttu-id="5696f-364">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-364">Forbidden.</span></span>|
|`enumeration`|<span data-ttu-id="5696f-365">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-365">Supported.</span></span> <span data-ttu-id="5696f-366">L'"id" dell'enumerazione viene ignorato e il "valore" esegue il mapping al nome del valore nel contratto dati di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5696f-366">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|
|`whiteSpace`|<span data-ttu-id="5696f-367">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-367">Forbidden.</span></span>|
|`pattern`|<span data-ttu-id="5696f-368">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-368">Forbidden.</span></span>|
|<span data-ttu-id="5696f-369">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="5696f-369">(empty)</span></span>|<span data-ttu-id="5696f-370">Supportato, esegue il mapping al tipo di enumerazione vuoto.</span><span class="sxs-lookup"><span data-stu-id="5696f-370">Supported, maps to empty enumeration type.</span></span>|

 <span data-ttu-id="5696f-371">Nel codice seguente viene illustrata una classe di enumerazione C#.</span><span class="sxs-lookup"><span data-stu-id="5696f-371">The following code shows a C# enumeration class.</span></span>

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

<span data-ttu-id="5696f-372">Questa classe esegue il mapping allo schema seguente da `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="5696f-372">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="5696f-373">Se i valori dell'enumerazione iniziano da 1, non vengono generati blocchi `xs:annotation` .</span><span class="sxs-lookup"><span data-stu-id="5696f-373">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>

```xml
<xs:simpleType name="MyEnum">
  <xs:restriction base="xs:string">
    <xs:enumeration value="first">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          3
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="second">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          4
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

### \<xs:list>

<span data-ttu-id="5696f-374">`DataContractSerializer` esegue il mapping dei tipi di enumerazione contrassegnati con `System.FlagsAttribute` a un `xs:list` derivato da `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="5696f-374">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="5696f-375">Non sono supportate altre variazioni di `xs:list` .</span><span class="sxs-lookup"><span data-stu-id="5696f-375">No other `xs:list` variations are supported.</span></span>

### <a name="xslist-attributes"></a><span data-ttu-id="5696f-376">\<xs:list>: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-376">\<xs:list>: attributes</span></span>

|<span data-ttu-id="5696f-377">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-377">Attribute</span></span>|<span data-ttu-id="5696f-378">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-378">Schema</span></span>|
|---------------|------------|
|`itemType`|<span data-ttu-id="5696f-379">Non consentito.</span><span class="sxs-lookup"><span data-stu-id="5696f-379">Forbidden.</span></span>|
|`id`|<span data-ttu-id="5696f-380">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-380">Ignored.</span></span>|

### <a name="xslist-contents"></a><span data-ttu-id="5696f-381">\<xs:list>: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-381">\<xs:list>: contents</span></span>

|<span data-ttu-id="5696f-382">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-382">Contents</span></span>|<span data-ttu-id="5696f-383">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-383">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5696f-384">Deve essere una restrizione da `xs:string` con utilizzo del facet `xs:enumeration` .</span><span class="sxs-lookup"><span data-stu-id="5696f-384">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|

<span data-ttu-id="5696f-385">Se il valore dell'enumerazione non segue una progressione per potenza di 2 (impostazione predefinita per i flag), viene memorizzato nell'elemento `xs:annotation/xs:appInfo/ser:EnumerationValue` .</span><span class="sxs-lookup"><span data-stu-id="5696f-385">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>

<span data-ttu-id="5696f-386">Ad esempio, nel codice seguente viene contrassegnato un tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5696f-386">For example, the following code flags an enumeration type.</span></span>

```csharp
[Flags]
public enum AuthFlags
{
  AuthAnonymous = 1,
  AuthBasic = 2,
  AuthNTLM = 4,
  AuthMD5 = 16,
  AuthWindowsLiveID = 64,
}
```

<span data-ttu-id="5696f-387">Questo tipo esegue il mapping allo schema seguente.</span><span class="sxs-lookup"><span data-stu-id="5696f-387">This type maps to the following schema.</span></span>

```xml
<xs:simpleType name="AuthFlags">
    <xs:list>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="AuthAnonymous" />
          <xs:enumeration value="AuthBasic" />
          <xs:enumeration value="AuthNTLM" />
          <xs:enumeration value="AuthMD5">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
          <xs:enumeration value="AuthWindowsLiveID">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
        </xs:restriction>
      </xs:simpleType>
    </xs:list>
  </xs:simpleType>
```

## <a name="inheritance"></a><span data-ttu-id="5696f-388">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="5696f-388">Inheritance</span></span>

### <a name="general-rules"></a><span data-ttu-id="5696f-389">Regole generali</span><span class="sxs-lookup"><span data-stu-id="5696f-389">General rules</span></span>

<span data-ttu-id="5696f-390">Un contratto dati può ereditare da un altro contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-390">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="5696f-391">Viene eseguito il mapping tra questi contratti dati, derivati da tipi di estensione tramite il costrutto dell'XML Schema `<xs:extension>` , e una base.</span><span class="sxs-lookup"><span data-stu-id="5696f-391">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>

<span data-ttu-id="5696f-392">Un contratto dati non può ereditare da un contratto dati di raccolta.</span><span class="sxs-lookup"><span data-stu-id="5696f-392">A data contract cannot inherit from a collection data contract.</span></span>

<span data-ttu-id="5696f-393">Ad esempio, nel codice seguente viene illustrato un contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-393">For example, the following code is a data contract.</span></span>

```csharp
[DataContract]
public class Person
{
  [DataMember]
  public string Name;
}
[DataContract]
public class Employee : Person
{
  [DataMember]
  public int ID;
}
```

<span data-ttu-id="5696f-394">Questo contratto dati esegue il mapping alla dichiarazione di tipo dell'XML Schema seguente.</span><span class="sxs-lookup"><span data-stu-id="5696f-394">This data contract maps to the following XML Schema type declaration.</span></span>

```xml
<xs:complexType name="Employee">
 <xs:complexContent mixed="false">
  <xs:extension base="tns:Person">
   <xs:sequence>
    <xs:element minOccurs="0" name="ID" type="xs:int"/>
   </xs:sequence>
  </xs:extension>
 </xs:complexContent>
</xs:complexType>
<xs:complexType name="Person">
 <xs:sequence>
  <xs:element minOccurs="0" name="Name"
    nillable="true" type="xs:string"/>
 </xs:sequence>
</xs:complexType>
```

### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="5696f-395">\<xs:complexContent>: attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-395">\<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="5696f-396">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-396">Attribute</span></span>|<span data-ttu-id="5696f-397">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-397">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="5696f-398">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-398">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="5696f-399">Deve essere false.</span><span class="sxs-lookup"><span data-stu-id="5696f-399">Must be false.</span></span>|

### <a name="xscomplexcontent-contents"></a><span data-ttu-id="5696f-400">\<xs:complexContent>: contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-400">\<xs:complexContent>: contents</span></span>

|<span data-ttu-id="5696f-401">Sommario</span><span class="sxs-lookup"><span data-stu-id="5696f-401">Contents</span></span>|<span data-ttu-id="5696f-402">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-402">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="5696f-403">Non consentito, tranne quando base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="5696f-403">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="5696f-404">L'ultima opzione equivale a posizionare il contenuto di `xs:restriction` direttamente sotto il contenitore di `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="5696f-404">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|
|`extension`|<span data-ttu-id="5696f-405">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-405">Supported.</span></span> <span data-ttu-id="5696f-406">Esegue il mapping all'ereditarietà del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-406">Maps to data contract inheritance.</span></span>|

### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="5696f-407">\<xs:extension>in \<xs:complexContent> : attributi</span><span class="sxs-lookup"><span data-stu-id="5696f-407">\<xs:extension> in \<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="5696f-408">Attributo</span><span class="sxs-lookup"><span data-stu-id="5696f-408">Attribute</span></span>|<span data-ttu-id="5696f-409">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5696f-409">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="5696f-410">Ignorato.</span><span class="sxs-lookup"><span data-stu-id="5696f-410">Ignored.</span></span>|
|`base`|<span data-ttu-id="5696f-411">Supportata.</span><span class="sxs-lookup"><span data-stu-id="5696f-411">Supported.</span></span> <span data-ttu-id="5696f-412">Esegue il mapping al tipo di contratto dati di base da cui questo tipo eredita.</span><span class="sxs-lookup"><span data-stu-id="5696f-412">Maps to the base data contract type that this type inherits from.</span></span>|

### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="5696f-413">\<xs:extension>in \<xs:complexContent> : contenuto</span><span class="sxs-lookup"><span data-stu-id="5696f-413">\<xs:extension> in \<xs:complexContent>: contents</span></span>

<span data-ttu-id="5696f-414">Le regole sono le stesse del contenuto `<xs:complexType>` .</span><span class="sxs-lookup"><span data-stu-id="5696f-414">The rules are the same as for `<xs:complexType>` contents.</span></span>

<span data-ttu-id="5696f-415">Se viene fornito un `<xs:sequence>` , i relativi elementi membro eseguono il mapping a membri dati aggiuntivi presenti nel contratto dati derivato.</span><span class="sxs-lookup"><span data-stu-id="5696f-415">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>

<span data-ttu-id="5696f-416">Se un tipo derivato contiene un elemento con lo stesso nome di un elemento in un tipo di base, la dichiarazione dell'elemento duplicato esegue il mapping a un membro dati con un nome generato per essere univoco.</span><span class="sxs-lookup"><span data-stu-id="5696f-416">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="5696f-417">Vengono aggiunti numeri interi positivi al nome del membro dati ("membro1", "membro2" e così via) fino a trovare un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="5696f-417">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="5696f-418">Al contrario:</span><span class="sxs-lookup"><span data-stu-id="5696f-418">Conversely:</span></span>

- <span data-ttu-id="5696f-419">Se un contratto dati derivato ha un membro dati con lo stesso nome e lo stesso tipo di un membro dati in un contratto dati di base, `DataContractSerializer` genera questo elemento corrispondente nel tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="5696f-419">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>

- <span data-ttu-id="5696f-420">Se un contratto dati derivato ha un membro dati con lo stesso nome di un membro dati in un contratto dati di base ma con un tipo diverso, `DataContractSerializer` importa uno schema con un elemento del tipo `xs:anyType` nelle dichiarazioni del tipo di base e del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="5696f-420">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="5696f-421">Il nome del tipo originale viene mantenuto in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span><span class="sxs-lookup"><span data-stu-id="5696f-421">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>

<span data-ttu-id="5696f-422">Entrambe le variazioni possono condurre a un schema con un modello di contenuto ambiguo, che dipende dall'ordine dei rispettivi membri dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-422">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>

## <a name="typeprimitive-mapping"></a><span data-ttu-id="5696f-423">Mapping di tipi/primitivi</span><span class="sxs-lookup"><span data-stu-id="5696f-423">Type/primitive mapping</span></span>

<span data-ttu-id="5696f-424">`DataContractSerializer` utilizza il mapping seguente per i tipi primitivi dello XML Schema.</span><span class="sxs-lookup"><span data-stu-id="5696f-424">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>

|<span data-ttu-id="5696f-425">Tipo XSD</span><span class="sxs-lookup"><span data-stu-id="5696f-425">XSD type</span></span>|<span data-ttu-id="5696f-426">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="5696f-426">.NET type</span></span>|
|--------------|---------------|
|`anyType`|<span data-ttu-id="5696f-427"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="5696f-427"><xref:System.Object>.</span></span>|
|`anySimpleType`|<span data-ttu-id="5696f-428"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-428"><xref:System.String>.</span></span>|
|`duration`|<span data-ttu-id="5696f-429"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="5696f-429"><xref:System.TimeSpan>.</span></span>|
|`dateTime`|<span data-ttu-id="5696f-430"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="5696f-430"><xref:System.DateTime>.</span></span>|
|`dateTimeOffset`|<span data-ttu-id="5696f-431"><xref:System.DateTime> e <xref:System.TimeSpan> per l'offset.</span><span class="sxs-lookup"><span data-stu-id="5696f-431"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="5696f-432">Vedere di seguito DateTimeOffset Serialization.</span><span class="sxs-lookup"><span data-stu-id="5696f-432">See DateTimeOffset Serialization below.</span></span>|
|`time`|<span data-ttu-id="5696f-433"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-433"><xref:System.String>.</span></span>|
|`date`|<span data-ttu-id="5696f-434"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-434"><xref:System.String>.</span></span>|
|`gYearMonth`|<span data-ttu-id="5696f-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-435"><xref:System.String>.</span></span>|
|`gYear`|<span data-ttu-id="5696f-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-436"><xref:System.String>.</span></span>|
|`gMonthDay`|<span data-ttu-id="5696f-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-437"><xref:System.String>.</span></span>|
|`gDay`|<span data-ttu-id="5696f-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-438"><xref:System.String>.</span></span>|
|`gMonth`|<span data-ttu-id="5696f-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-439"><xref:System.String>.</span></span>|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|<span data-ttu-id="5696f-440">Matrice <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="5696f-440"><xref:System.Byte> array.</span></span>|
|`hexBinary`|<span data-ttu-id="5696f-441"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-441"><xref:System.String>.</span></span>|
|`float`|<span data-ttu-id="5696f-442"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="5696f-442"><xref:System.Single>.</span></span>|
|`double`|<span data-ttu-id="5696f-443"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="5696f-443"><xref:System.Double>.</span></span>|
|`anyURI`|<span data-ttu-id="5696f-444"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="5696f-444"><xref:System.Uri>.</span></span>|
|`QName`|<span data-ttu-id="5696f-445"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="5696f-445"><xref:System.Xml.XmlQualifiedName>.</span></span>|
|`string`|<span data-ttu-id="5696f-446"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-446"><xref:System.String>.</span></span>|
|`normalizedString`|<span data-ttu-id="5696f-447"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-447"><xref:System.String>.</span></span>|
|`token`|<span data-ttu-id="5696f-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-448"><xref:System.String>.</span></span>|
|`language`|<span data-ttu-id="5696f-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-449"><xref:System.String>.</span></span>|
|`Name`|<span data-ttu-id="5696f-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-450"><xref:System.String>.</span></span>|
|`NCName`|<span data-ttu-id="5696f-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-451"><xref:System.String>.</span></span>|
|`ID`|<span data-ttu-id="5696f-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-452"><xref:System.String>.</span></span>|
|`IDREF`|<span data-ttu-id="5696f-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-453"><xref:System.String>.</span></span>|
|`IDREFS`|<span data-ttu-id="5696f-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-454"><xref:System.String>.</span></span>|
|`ENTITY`|<span data-ttu-id="5696f-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-455"><xref:System.String>.</span></span>|
|`ENTITIES`|<span data-ttu-id="5696f-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-456"><xref:System.String>.</span></span>|
|`NMTOKEN`|<span data-ttu-id="5696f-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-457"><xref:System.String>.</span></span>|
|`NMTOKENS`|<span data-ttu-id="5696f-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5696f-458"><xref:System.String>.</span></span>|
|`decimal`|<span data-ttu-id="5696f-459"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="5696f-459"><xref:System.Decimal>.</span></span>|
|`integer`|<span data-ttu-id="5696f-460"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-460"><xref:System.Int64>.</span></span>|
|`nonPositiveInteger`|<span data-ttu-id="5696f-461"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-461"><xref:System.Int64>.</span></span>|
|`negativeInteger`|<span data-ttu-id="5696f-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-462"><xref:System.Int64>.</span></span>|
|`long`|<span data-ttu-id="5696f-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-463"><xref:System.Int64>.</span></span>|
|`int`|<span data-ttu-id="5696f-464"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="5696f-464"><xref:System.Int32>.</span></span>|
|`short`|<span data-ttu-id="5696f-465"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="5696f-465"><xref:System.Int16>.</span></span>|
|`Byte`|<span data-ttu-id="5696f-466"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="5696f-466"><xref:System.SByte>.</span></span>|
|`nonNegativeInteger`|<span data-ttu-id="5696f-467"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-467"><xref:System.Int64>.</span></span>|
|`unsignedLong`|<span data-ttu-id="5696f-468"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-468"><xref:System.UInt64>.</span></span>|
|`unsignedInt`|<span data-ttu-id="5696f-469"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="5696f-469"><xref:System.UInt32>.</span></span>|
|`unsignedShort`|<span data-ttu-id="5696f-470"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="5696f-470"><xref:System.UInt16>.</span></span>|
|`unsignedByte`|<span data-ttu-id="5696f-471"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="5696f-471"><xref:System.Byte>.</span></span>|
|`positiveInteger`|<span data-ttu-id="5696f-472"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5696f-472"><xref:System.Int64>.</span></span>|

## <a name="iserializable-types-mapping"></a><span data-ttu-id="5696f-473">Mapping dei tipi ISerializable</span><span class="sxs-lookup"><span data-stu-id="5696f-473">ISerializable types mapping</span></span>

<span data-ttu-id="5696f-474">In .NET Framework versione 1,0, <xref:System.Runtime.Serialization.ISerializable> è stato introdotto come meccanismo generale per serializzare gli oggetti per la persistenza o il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-474">In .NET Framework version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="5696f-475">Sono disponibili molti tipi di .NET Framework che implementano `ISerializable` e che possono essere passati tra le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5696f-475">There are many .NET Framework types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="5696f-476"><xref:System.Runtime.Serialization.DataContractSerializer> fornisce naturalmente il supporto per le classi `ISerializable` .</span><span class="sxs-lookup"><span data-stu-id="5696f-476"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="5696f-477">`DataContractSerializer` esegue il mapping ai tipi dello schema di implementazione di `ISerializable` che differiscono solo per il QName (nome completo) del tipo e sono effettivamente raccolte di proprietà.</span><span class="sxs-lookup"><span data-stu-id="5696f-477">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="5696f-478">Ad esempio, `DataContractSerializer` esegue il mapping <xref:System.Exception> al tipo XSD seguente nello `http://schemas.datacontract.org/2004/07/System` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5696f-478">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

<span data-ttu-id="5696f-479">L'attributo facoltativo `ser:FactoryType` dichiarato nello schema di serializzazione del contratto dati fa riferimento a una classe factory che può deserializzare il tipo.</span><span class="sxs-lookup"><span data-stu-id="5696f-479">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="5696f-480">La classe factory deve far parte della raccolta dei tipi noti dell'istanza di `DataContractSerializer` utilizzata.</span><span class="sxs-lookup"><span data-stu-id="5696f-480">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="5696f-481">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="5696f-481">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span>

## <a name="datacontract-serialization-schema"></a><span data-ttu-id="5696f-482">Schema di serializzazione del contratto dati</span><span class="sxs-lookup"><span data-stu-id="5696f-482">DataContract Serialization Schema</span></span>

<span data-ttu-id="5696f-483">Diversi schemi esportati da `DataContractSerializer` utilizzano tipi, elementi e attributi da uno speciale spazio dei nomi di serializzazione del contratto dati:</span><span class="sxs-lookup"><span data-stu-id="5696f-483">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>

`http://schemas.microsoft.com/2003/10/Serialization`

<span data-ttu-id="5696f-484">Di seguito è riportata una dichiarazione completa dello schema di serializzazione del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="5696f-484">The following is a complete Data Contract Serialization schema declaration.</span></span>

```xml
<xs:schema attributeFormDefault="qualified"
   elementFormDefault="qualified"
   targetNamespace =
    "http://schemas.microsoft.com/2003/10/Serialization/"
   xmlns:xs="http://www.w3.org/2001/XMLSchema"
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">

 <!-- Top-level elements for primitive types. -->
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>
 <xs:element name="base64Binary"
       nillable="true" type="xs:base64Binary"/>
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>
 <xs:element name="byte" nillable="true" type="xs:byte"/>
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>
 <xs:element name="double" nillable="true" type="xs:double"/>
 <xs:element name="float" nillable="true" type="xs:float"/>
 <xs:element name="int" nillable="true" type="xs:int"/>
 <xs:element name="long" nillable="true" type="xs:long"/>
 <xs:element name="QName" nillable="true" type="xs:QName"/>
 <xs:element name="short" nillable="true" type="xs:short"/>
 <xs:element name="string" nillable="true" type="xs:string"/>
 <xs:element name="unsignedByte"
       nillable="true" type="xs:unsignedByte"/>
 <xs:element name="unsignedInt"
       nillable="true" type="xs:unsignedInt"/>
 <xs:element name="unsignedLong"
       nillable="true" type="xs:unsignedLong"/>
 <xs:element name="unsignedShort"
       nillable="true" type="xs:unsignedShort"/>

 <!-- Primitive types introduced for certain .NET simple types. -->
 <xs:element name="char" nillable="true" type="tns:char"/>
 <xs:simpleType name="char">
  <xs:restriction base="xs:int"/>
 </xs:simpleType>

 <!-- xs:duration is restricted to an ordered value space,
    to map to System.TimeSpan -->
 <xs:element name="duration" nillable="true" type="tns:duration"/>
 <xs:simpleType name="duration">
  <xs:restriction base="xs:duration">
   <xs:pattern
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>
  </xs:restriction>
 </xs:simpleType>

 <xs:element name="guid" nillable="true" type="tns:guid"/>
 <xs:simpleType name="guid">
  <xs:restriction base="xs:string">
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>
  </xs:restriction>
 </xs:simpleType>

 <!-- This is used for schemas exported from ISerializable type. -->
 <xs:attribute name="FactoryType" type="xs:QName"/>
</xs:schema>
```

<span data-ttu-id="5696f-485">È necessario tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5696f-485">The following should be noted:</span></span>

- <span data-ttu-id="5696f-486">`ser:char` viene introdotto per rappresentare caratteri Unicode di tipo <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="5696f-486">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>

- <span data-ttu-id="5696f-487">Il `valuespace` di `xs:duration` viene ridotto a una raccolta ordinata, in modo che possa essere associato a un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="5696f-487">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>

- <span data-ttu-id="5696f-488">`FactoryType` viene utilizzato negli schemi esportati da tipi derivati da <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="5696f-488">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>

## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="5696f-489">Importazione di schemi non di contratto dati</span><span class="sxs-lookup"><span data-stu-id="5696f-489">Importing non-DataContract schemas</span></span>

<span data-ttu-id="5696f-490">`DataContractSerializer` dispone dell'opzione `ImportXmlTypes` per consentire l'importazione di schemi non conformi al profilo XSD `DataContractSerializer` (vedere la proprietà <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ).</span><span class="sxs-lookup"><span data-stu-id="5696f-490">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="5696f-491">Se si imposta questa opzione su `true` , si consente l'accettazione di tipi di schema non conformi e il mapping di questi ultimi all'implementazione seguente, con <xref:System.Xml.Serialization.IXmlSerializable> che esegue il wrapping di una matrice di <xref:System.Xml.XmlNode> (differisce solo il nome della classe).</span><span class="sxs-lookup"><span data-stu-id="5696f-491">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>

```csharp
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]
public partial class Person : object, IXmlSerializable
{
  private XmlNode[] nodesField;
  private static XmlQualifiedName typeName =
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");
  public XmlNode[] Nodes
  {
    get {return this.nodesField;}
    set {this.nodesField = value;}
  }
  public void ReadXml(XmlReader reader)
  {
    this.nodesField = XmlSerializableServices.ReadNodes(reader);
  }
  public void WriteXml(XmlWriter writer)
  {
    XmlSerializableServices.WriteNodes(writer, this.Nodes);
  }
  public System.Xml.Schema.XmlSchema GetSchema()
  {
    return null;
  }
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)
  {
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);
    return typeName;
  }
}
```

## <a name="datetimeoffset-serialization"></a><span data-ttu-id="5696f-492">Serializzazione DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5696f-492">DateTimeOffset Serialization</span></span>

<span data-ttu-id="5696f-493"><xref:System.DateTimeOffset> non viene considerato un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="5696f-493">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="5696f-494">Viene invece serializzato come elemento complesso con due parti.</span><span class="sxs-lookup"><span data-stu-id="5696f-494">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="5696f-495">La prima parte rappresenta il valore data/ora e la seconda parte rappresenta l'offset dal valore data/ora.</span><span class="sxs-lookup"><span data-stu-id="5696f-495">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="5696f-496">Nel codice seguente viene illustrato un esempio di valore DateTimeOffset serializzato.</span><span class="sxs-lookup"><span data-stu-id="5696f-496">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>

```xml
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">
  <DateTime i:type="b:dateTime" xmlns=""
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00
  </DateTime>
  <OffsetMinutes i:type="b:short" xmlns=""
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480
   </OffsetMinutes>
</OffSet>
```

<span data-ttu-id="5696f-497">Lo schema è il seguente.</span><span class="sxs-lookup"><span data-stu-id="5696f-497">The schema is as follows.</span></span>

```xml
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">
   <xs:complexType name="DateTimeOffset">
      <xs:sequence minOccurs="1" maxOccurs="1">
         <xs:element name="DateTime" type="xs:dateTime"
         minOccurs="1" maxOccurs="1" />
         <xs:element name="OffsetMinutes" type="xs:short"
         minOccurs="1" maxOccurs="1" />
      </xs:sequence>
   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a><span data-ttu-id="5696f-498">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5696f-498">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="5696f-499">Using Data Contracts</span><span class="sxs-lookup"><span data-stu-id="5696f-499">Using Data Contracts</span></span>](using-data-contracts.md)
