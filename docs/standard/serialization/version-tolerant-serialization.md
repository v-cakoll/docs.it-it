---
title: Serializzazione indipendente dalla versione
description: Il .NET Framework 2,0 introduce la serializzazione a tolleranza di versione, un set di funzionalità che semplificano la modifica dei tipi serializzabili.
ms.date: 08/08/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- version tolerant serialization
- serialization, custom serialization
- serialization, version tolerant
- serialization, controlling
- versions and serialization
- BinaryFormatter class, samples
- serialization, attributes
ms.assetid: bea0ffe3-2708-4a16-ac7d-e586ed6b8e8d
ms.openlocfilehash: 87bdc0f0328e7a75477672432c0944818dbef244
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380086"
---
# <a name="version-tolerant-serialization"></a><span data-ttu-id="2e082-103">Serializzazione indipendente dalla versione</span><span class="sxs-lookup"><span data-stu-id="2e082-103">Version tolerant serialization</span></span>

<span data-ttu-id="2e082-104">Nelle versioni 1.0 e 1.1 di .NET Framework, la creazione di tipi serializzabili riutilizzabili da una versione di un'applicazione alla versione successiva risultava problematica.</span><span class="sxs-lookup"><span data-stu-id="2e082-104">In version 1.0 and 1.1 of the .NET Framework, creating serializable types that would be reusable from one version of an application to the next was problematic.</span></span> <span data-ttu-id="2e082-105">Se un tipo veniva modificato aggiungendo campi aggiuntivi, si verificavano i seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="2e082-105">If a type was modified by adding extra fields, the following problems would occur:</span></span>

- <span data-ttu-id="2e082-106">Le versioni precedenti di un'applicazione avrebbero generato eccezioni durante la richiesta di deserializzazione delle nuove versioni del tipo obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2e082-106">Older versions of an application would throw exceptions when asked to deserialize new versions of the old type.</span></span>
- <span data-ttu-id="2e082-107">Le versioni più recenti di un'applicazione avrebbero generato eccezioni durante la deserializzazione delle versioni precedenti di un tipo con dati mancanti.</span><span class="sxs-lookup"><span data-stu-id="2e082-107">Newer versions of an application would throw exceptions when deserializing older versions of a type with missing data.</span></span>

<span data-ttu-id="2e082-108">La Serializzazione a tolleranza di versione (VTS, Version Tolerant Serialization) è un set di funzionalità introdotto in .NET Framework 2.0 che semplifica, nel tempo, la modifica dei tipi serializzabili.</span><span class="sxs-lookup"><span data-stu-id="2e082-108">Version Tolerant Serialization (VTS) is a set of features introduced in .NET Framework 2.0 that makes it easier, over time, to modify serializable types.</span></span> <span data-ttu-id="2e082-109">In particolare, le funzionalità VTS vengono abilitate per le classi alle quali è stato applicato l'attributo <xref:System.SerializableAttribute>, inclusi i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="2e082-109">Specifically, the VTS features are enabled for classes to which the <xref:System.SerializableAttribute> attribute has been applied, including generic types.</span></span> <span data-ttu-id="2e082-110">VTS rende possibile l'aggiunta di nuovi campi a tali classi senza compromettere la compatibilità con le altre versioni del tipo.</span><span class="sxs-lookup"><span data-stu-id="2e082-110">VTS makes it possible to add new fields to those classes without breaking compatibility with other versions of the type.</span></span> <span data-ttu-id="2e082-111">Per un'applicazione di esempio funzionante, vedere [Esempio di tecnologia di serializzazione indipendente dalla versione](version-tolerant-serialization-technology-sample.md).</span><span class="sxs-lookup"><span data-stu-id="2e082-111">For a working sample application, see [Version Tolerant Serialization Technology Sample](version-tolerant-serialization-technology-sample.md).</span></span>

<span data-ttu-id="2e082-112">Le funzionalità VTS vengono abilitate durante l'utilizzo di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="2e082-112">The VTS features are enabled when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="2e082-113">Inoltre, durante l'utilizzo di <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, sono abilitate tutte le funzionalità salvo la tolleranza di dati estranei.</span><span class="sxs-lookup"><span data-stu-id="2e082-113">Additionally, all features except extraneous data tolerance are also enabled when using the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="2e082-114">Per altre informazioni sull'uso di queste classi per la serializzazione, vedere [Serializzazione binaria](binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="2e082-114">For more information about using these classes for serialization, see [Binary Serialization](binary-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a><span data-ttu-id="2e082-115">Elenco di funzionalità</span><span class="sxs-lookup"><span data-stu-id="2e082-115">Feature list</span></span>

<span data-ttu-id="2e082-116">Il set di funzionalità comprende quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2e082-116">The set of features includes the following:</span></span>

- <span data-ttu-id="2e082-117">Tolleranza di dati estranei o imprevisti.</span><span class="sxs-lookup"><span data-stu-id="2e082-117">Tolerance of extraneous or unexpected data.</span></span> <span data-ttu-id="2e082-118">Consente a versioni più recenti del tipo di inviare dati alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2e082-118">This enables newer versions of the type to send data to older versions.</span></span>
- <span data-ttu-id="2e082-119">Tolleranza di dati facoltativi mancanti.</span><span class="sxs-lookup"><span data-stu-id="2e082-119">Tolerance of missing optional data.</span></span> <span data-ttu-id="2e082-120">Consente a versioni precedenti di inviare dati alle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="2e082-120">This enables older versions to send data to newer versions.</span></span>
- <span data-ttu-id="2e082-121">Callback di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-121">Serialization callbacks.</span></span> <span data-ttu-id="2e082-122">Consente l'impostazione intelligente del valore predefinito nei casi in cui dei dati siano mancanti.</span><span class="sxs-lookup"><span data-stu-id="2e082-122">This enables intelligent default value setting in cases where data is missing.</span></span>

<span data-ttu-id="2e082-123">In aggiunta, è presente una funzionalità che consente di dichiarare l'aggiunta di un nuovo campo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2e082-123">In addition, there is a feature for declaring when a new optional field has been added.</span></span> <span data-ttu-id="2e082-124">Questa è la proprietà <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> dell'attributo <xref:System.Runtime.Serialization.OptionalFieldAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2e082-124">This is the <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> property of the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute.</span></span>

<span data-ttu-id="2e082-125">Queste funzionalità sono descritte più dettagliatamente nelle sezioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="2e082-125">These features are discussed in greater detail in the following sections.</span></span>

### <a name="tolerance-of-extraneous-or-unexpected-data"></a><span data-ttu-id="2e082-126">Tolleranza di dati estranei o imprevisti</span><span class="sxs-lookup"><span data-stu-id="2e082-126">Tolerance of extraneous or unexpected data</span></span>

<span data-ttu-id="2e082-127">In passato, durante la serializzazione, la presenza di dati estranei o imprevisti generava eccezioni.</span><span class="sxs-lookup"><span data-stu-id="2e082-127">In the past, during deserialization, any extraneous or unexpected data caused exceptions to be thrown.</span></span> <span data-ttu-id="2e082-128">Con VTS, nella stessa situazione, eventuali dati estranei o imprevisti vengono ignorati piuttosto che generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="2e082-128">With VTS, in the same situation, any extraneous or unexpected data is ignored instead of causing exceptions to be thrown.</span></span> <span data-ttu-id="2e082-129">Ciò consente alle applicazioni che utilizzano versioni più recenti di un tipo (ovvero una versione che include più campi) di inviare informazioni alle applicazioni che prevedono versioni precedenti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="2e082-129">This enables applications that use newer versions of a type (that is, a version that includes more fields) to send information to applications that expect older versions of the same type.</span></span>

<span data-ttu-id="2e082-130">Nell'esempio riportato di seguito, i dati aggiuntivi contenuti in `CountryField` della versione 2.0 della classe `Address` vengono ignorati nel momento in cui un'applicazione precedente deserializza la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="2e082-130">In the following example, the extra data contained in the `CountryField` of version 2.0 of the `Address` class is ignored when an older application deserializes the newer version.</span></span>

```csharp  
// Version 1 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
}  
// Version 2.0 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    // The older application ignores this data.  
    public string CountryField;  
}  
```  
  
```vb  
' Version 1 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
End Class  
  
' Version 2.0 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    ' The older application ignores this data.  
    Public CountryField As String  
End Class  
```  

### <a name="tolerance-of-missing-data"></a><span data-ttu-id="2e082-131">Tolleranza di dati mancanti</span><span class="sxs-lookup"><span data-stu-id="2e082-131">Tolerance of missing data</span></span>

<span data-ttu-id="2e082-132">I campi possono essere contrassegnati come facoltativi applicando ad essi l'attributo <xref:System.Runtime.Serialization.OptionalFieldAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2e082-132">Fields can be marked as optional by applying the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to them.</span></span> <span data-ttu-id="2e082-133">Durante la deserializzazione, se i dati facoltativi risultano mancanti, il motore di serializzazione ignora tale assenza e non genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="2e082-133">During deserialization, if the optional data is missing, the serialization engine ignores the absence and does not throw an exception.</span></span> <span data-ttu-id="2e082-134">In tal modo, le applicazioni che prevedono versioni precedenti di un tipo, possono inviare dati ad applicazioni che prevedono versioni più recenti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="2e082-134">Thus, applications that expect older versions of a type can send data to applications that expect newer versions of the same type.</span></span>

<span data-ttu-id="2e082-135">Nell'esempio riportato di seguito viene mostrata la versione 2.0 della classe `Address` con il campo `CountryField` contrassegnato come facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2e082-135">The following example shows version 2.0 of the `Address` class with the `CountryField` field marked as optional.</span></span> <span data-ttu-id="2e082-136">Se un'applicazione precedente invia la versione 1 a un'applicazione più recente che prevede la versione 2.0, l'assenza dei dati viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="2e082-136">If an older application sends version 1 to a newer application that expects version 2.0, the absence of the data is ignored.</span></span>

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;

    [OptionalField]
    public string CountryField;
}
```

```vb
<Serializable> _
Public Class Address
    Public Street As String
    Public City As String

    <OptionalField> _
    Public CountryField As String
End Class
```
  
### <a name="serialization-callbacks"></a><span data-ttu-id="2e082-137">Callback di serializzazione</span><span class="sxs-lookup"><span data-stu-id="2e082-137">Serialization callbacks</span></span>

<span data-ttu-id="2e082-138">I callback di serializzazione rappresentano un meccanismo che fornisce hook nel processo di serializzazione/deserializzazione in quattro punti.</span><span class="sxs-lookup"><span data-stu-id="2e082-138">Serialization callbacks are a mechanism that provides hooks into the serialization/deserialization process at four points.</span></span>

|<span data-ttu-id="2e082-139">Attributo</span><span class="sxs-lookup"><span data-stu-id="2e082-139">Attribute</span></span>|<span data-ttu-id="2e082-140">Quando viene chiamato il metodo associato</span><span class="sxs-lookup"><span data-stu-id="2e082-140">When the Associated Method is Called</span></span>|<span data-ttu-id="2e082-141">Utilizzo tipico</span><span class="sxs-lookup"><span data-stu-id="2e082-141">Typical Use</span></span>|
|---------------|------------------------------------------|-----------------|
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="2e082-142">Prima della deserializzazione.\*</span><span class="sxs-lookup"><span data-stu-id="2e082-142">Before deserialization.\*</span></span>|<span data-ttu-id="2e082-143">Inizializzare i valori predefiniti per i campi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="2e082-143">Initialize default values for optional fields.</span></span>|
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="2e082-144">Dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-144">After deserialization.</span></span>|<span data-ttu-id="2e082-145">Correggere i valori dei campi facoltativi in base al contenuto di altri campi.</span><span class="sxs-lookup"><span data-stu-id="2e082-145">Fix optional field values based on contents of other fields.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="2e082-146">Prima della serializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-146">Before serialization.</span></span>|<span data-ttu-id="2e082-147">Preparare per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-147">Prepare for serialization.</span></span> <span data-ttu-id="2e082-148">Ad esempio, la creazione di strutture di dati facoltativi.</span><span class="sxs-lookup"><span data-stu-id="2e082-148">For example, create optional data structures.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="2e082-149">Dopo la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-149">After serialization.</span></span>|<span data-ttu-id="2e082-150">Registrare gli eventi di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-150">Log serialization events.</span></span>|

 <span data-ttu-id="2e082-151">\* Questo callback viene richiamato prima del costruttore di deserializzazione, se presente.</span><span class="sxs-lookup"><span data-stu-id="2e082-151">\* This callback is invoked before the deserialization constructor, if one is present.</span></span>

#### <a name="using-callbacks"></a><span data-ttu-id="2e082-152">Uso dei callback</span><span class="sxs-lookup"><span data-stu-id="2e082-152">Using callbacks</span></span>

<span data-ttu-id="2e082-153">Per utilizzare i callback, applicare l'attributo appropriato a un metodo che accetta un parametro <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="2e082-153">To use callbacks, apply the appropriate attribute to a method that accepts a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span> <span data-ttu-id="2e082-154">È possibile contrassegnare solo uno metodo per classe con ciascuno di questi attributi.</span><span class="sxs-lookup"><span data-stu-id="2e082-154">Only one method per class can be marked with each of these attributes.</span></span> <span data-ttu-id="2e082-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2e082-155">For example:</span></span>

```csharp
[OnDeserializing]
private void SetCountryRegionDefault(StreamingContext sc)
{
    CountryField = "Japan";
}
```

```vb
<OnDeserializing>
Private Sub SetCountryRegionDefault(sc As StreamingContext)
    CountryField = "Japan"
End Sub
```

<span data-ttu-id="2e082-156">L'utilizzo di questi metodi è destinato al controllo la versione.</span><span class="sxs-lookup"><span data-stu-id="2e082-156">The intended use of these methods is for versioning.</span></span> <span data-ttu-id="2e082-157">Durante la deserializzazione, un campo facoltativo potrebbe non essere inizializzato correttamente nel caso in cui i dati del campo risultino mancanti.</span><span class="sxs-lookup"><span data-stu-id="2e082-157">During deserialization, an optional field may not be correctly initialized if the data for the field is missing.</span></span> <span data-ttu-id="2e082-158">Ciò può essere corretto creando il metodo che assegna il valore appropriato e quindi applicando l'attributo **OnDeserializingAttribute** o **OnDeserializedAttribute** al metodo.</span><span class="sxs-lookup"><span data-stu-id="2e082-158">This can be corrected by creating the method that assigns the correct value, then applying either the **OnDeserializingAttribute** or **OnDeserializedAttribute** attribute to the method.</span></span>

<span data-ttu-id="2e082-159">Nell'esempio riportato di seguito, viene mostrato il metodo nel contesto di un tipo.</span><span class="sxs-lookup"><span data-stu-id="2e082-159">The following example shows the method in the context of a type.</span></span> <span data-ttu-id="2e082-160">Se una versione precedente di un'applicazione invia un'istanza della classe `Address` a una versione più recente dell'applicazione, i dati del campo `CountryField` risulteranno mancanti.</span><span class="sxs-lookup"><span data-stu-id="2e082-160">If an earlier version of an application sends an instance of the `Address` class to a later version of the application, the `CountryField` field data will be missing.</span></span> <span data-ttu-id="2e082-161">Ma dopo la deserializzazione, il campo verrà impostato su un valore predefinito "Japan".</span><span class="sxs-lookup"><span data-stu-id="2e082-161">But after deserialization, the field will be set to a default value "Japan".</span></span>

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;
    [OptionalField]
    public string CountryField;

    [OnDeserializing]
    private void SetCountryRegionDefault(StreamingContext sc)
    {
        CountryField = "Japan";
    }
}
```

```vb
<Serializable> _
Public Class Address
    Public Street As String
    Public City As String
    <OptionalField> _
    Public CountryField As String

    <OnDeserializing> _
    Private Sub SetCountryRegionDefault(sc As StreamingContext)
        CountryField = "Japan"
    End Sub
End Class
```

## <a name="the-versionadded-property"></a><span data-ttu-id="2e082-162">Proprietà VersionAdded</span><span class="sxs-lookup"><span data-stu-id="2e082-162">The VersionAdded property</span></span>

<span data-ttu-id="2e082-163">L'oggetto **OptionalFieldAttribute** ha la proprietà **VersionAdded**.</span><span class="sxs-lookup"><span data-stu-id="2e082-163">The **OptionalFieldAttribute** has the **VersionAdded** property.</span></span> <span data-ttu-id="2e082-164">In .NET Framework versione 2.0 tale proprietà non viene usata.</span><span class="sxs-lookup"><span data-stu-id="2e082-164">In version 2.0 of the .NET Framework, this isn't used.</span></span> <span data-ttu-id="2e082-165">È tuttavia importante impostare correttamente questa proprietà in modo da essere certi che il tipo sia compatibile con i motori di serializzazione futuri.</span><span class="sxs-lookup"><span data-stu-id="2e082-165">However, it's important to set this property correctly to ensure that the type will be compatible with future serialization engines.</span></span>

<span data-ttu-id="2e082-166">La proprietà indica quale versione di un tipo di un determinato campo è stata aggiunta.</span><span class="sxs-lookup"><span data-stu-id="2e082-166">The property indicates which version of a type a given field has been added.</span></span> <span data-ttu-id="2e082-167">È necessario che venga incrementato esattamente di uno (a partire da 2) ogni volta che viene modificato il tipo, come mostra l'esempio riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2e082-167">It should be incremented by exactly one (starting at 2) every time the type is modified, as shown in the following example:</span></span>

```csharp
// Version 1.0
[Serializable]
public class Person
{
    public string FullName;
}

// Version 2.0
[Serializable]
public class Person
{
    public string FullName;

    [OptionalField(VersionAdded = 2)]
    public string NickName;
    [OptionalField(VersionAdded = 2)]
    public DateTime BirthDate;
}

// Version 3.0
[Serializable]
public class Person
{
    public string FullName;

    [OptionalField(VersionAdded=2)]
    public string NickName;
    [OptionalField(VersionAdded=2)]
    public DateTime BirthDate;

    [OptionalField(VersionAdded=3)]
    public int Weight;
}
```

```vb
' Version 1.0
<Serializable> _
Public Class Person
    Public FullName
End Class

' Version 2.0
<Serializable> _
Public Class Person
    Public FullName As String

    <OptionalField(VersionAdded := 2)> _
    Public NickName As String
    <OptionalField(VersionAdded := 2)> _
    Public BirthDate As DateTime
End Class

' Version 3.0
<Serializable> _
Public Class Person
    Public FullName As String

    <OptionalField(VersionAdded := 2)> _
    Public NickName As String
    <OptionalField(VersionAdded := 2)> _
    Public BirthDate As DateTime

    <OptionalField(VersionAdded := 3)> _
    Public Weight As Integer
End Class
```

## <a name="serializationbinder"></a><span data-ttu-id="2e082-168">SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="2e082-168">SerializationBinder</span></span>

<span data-ttu-id="2e082-169">In alcuni casi potrebbe essere necessario controllare le classi da serializzare e deserializzare ad esempio perché sono richieste versioni diverse della classe sul server e sul client.</span><span class="sxs-lookup"><span data-stu-id="2e082-169">Some users may need to control which class to serialize and deserialize because a different version of the class is required on the server and client.</span></span> <span data-ttu-id="2e082-170"><xref:System.Runtime.Serialization.SerializationBinder> è una classe astratta usata per controllare i tipi effettivi usati durante la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="2e082-170"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="2e082-171">Per utilizzare questa classe, derivare una classe da <xref:System.Runtime.Serialization.SerializationBinder> ed eseguire l'override dei metodi <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> e <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>,</span><span class="sxs-lookup"><span data-stu-id="2e082-171">To use this class, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> methods.</span></span> <span data-ttu-id="2e082-172">Per altre informazioni, vedere [controllo della serializzazione e deserializzazione con SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span><span class="sxs-lookup"><span data-stu-id="2e082-172">For more information, see [Controlling Serialization and Deserialization with SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span></span>

## <a name="best-practices"></a><span data-ttu-id="2e082-173">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="2e082-173">Best practices</span></span>

<span data-ttu-id="2e082-174">Per essere certi del comportamento corretto del controllo della versione, attenersi a queste regole durante la modifica di un tipo da una versione a un'altra:</span><span class="sxs-lookup"><span data-stu-id="2e082-174">To ensure proper versioning behavior, follow these rules when modifying a type from version to version:</span></span>

- <span data-ttu-id="2e082-175">Non rimuovere mai un campo serializzato.</span><span class="sxs-lookup"><span data-stu-id="2e082-175">Never remove a serialized field.</span></span>
- <span data-ttu-id="2e082-176">Non applicare mai l'attributo <xref:System.NonSerializedAttribute> a un campo se l'attributo non è stato applicato al campo nella versione precedente.</span><span class="sxs-lookup"><span data-stu-id="2e082-176">Never apply the <xref:System.NonSerializedAttribute> attribute to a field if the attribute was not applied to the field in the previous version.</span></span>
- <span data-ttu-id="2e082-177">Non modificare mai il nome o il tipo di un campo serializzato.</span><span class="sxs-lookup"><span data-stu-id="2e082-177">Never change the name or the type of a serialized field.</span></span>
- <span data-ttu-id="2e082-178">Quando si aggiunge un nuovo campo serializzato, applicare l'attributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="2e082-178">When adding a new serialized field, apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="2e082-179">Quando si rimuove un attributo **NonSerializedAttribute** da un campo (non serializzabile in una versione precedente), applicare l'attributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="2e082-179">When removing a **NonSerializedAttribute** attribute from a field (that was not serializable in a previous version), apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="2e082-180">Per tutti i campi facoltativi, impostare valori predefiniti significativi usando callback di serializzazione, a meno che non risultino accettabili 0 o **Null** come valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2e082-180">For all optional fields, set meaningful defaults using the serialization callbacks unless 0 or **null** as defaults are acceptable.</span></span>

<span data-ttu-id="2e082-181">Per essere certi che un tipo sia compatibile con i motori di serializzazione futuri, seguire le linee guida riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="2e082-181">To ensure that a type will be compatible with future serialization engines, follow these guidelines:</span></span>

- <span data-ttu-id="2e082-182">Impostare sempre la proprietà **VersionAdded** sull'attributo **OptionalFieldAttribute** in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="2e082-182">Always set the **VersionAdded** property on the **OptionalFieldAttribute** attribute correctly.</span></span>
- <span data-ttu-id="2e082-183">Evitare controlli di versione sottoposti a branching.</span><span class="sxs-lookup"><span data-stu-id="2e082-183">Avoid branched versioning.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e082-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e082-184">See also</span></span>

- <xref:System.SerializableAttribute>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- <xref:System.NonSerializedAttribute>
- [<span data-ttu-id="2e082-185">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="2e082-185">Binary Serialization</span></span>](binary-serialization.md)
