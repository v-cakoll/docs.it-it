---
title: Serializzazione indipendente dalla versione
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
ms.openlocfilehash: 9886e2f20ef7954b01ea1f46a9eabdb9ea2cc12d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348439"
---
# <a name="version-tolerant-serialization"></a><span data-ttu-id="68e67-102">Serializzazione indipendente dalla versione</span><span class="sxs-lookup"><span data-stu-id="68e67-102">Version tolerant serialization</span></span>

<span data-ttu-id="68e67-103">Nelle versioni 1.0 e 1.1 di .NET Framework, la creazione di tipi serializzabili riutilizzabili da una versione di un'applicazione alla versione successiva risultava problematica.</span><span class="sxs-lookup"><span data-stu-id="68e67-103">In version 1.0 and 1.1 of the .NET Framework, creating serializable types that would be reusable from one version of an application to the next was problematic.</span></span> <span data-ttu-id="68e67-104">Se un tipo veniva modificato aggiungendo campi aggiuntivi, si verificavano i seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="68e67-104">If a type was modified by adding extra fields, the following problems would occur:</span></span>

- <span data-ttu-id="68e67-105">Le versioni precedenti di un'applicazione avrebbero generato eccezioni durante la richiesta di deserializzazione delle nuove versioni del tipo obsoleto.</span><span class="sxs-lookup"><span data-stu-id="68e67-105">Older versions of an application would throw exceptions when asked to deserialize new versions of the old type.</span></span>
- <span data-ttu-id="68e67-106">Le versioni più recenti di un'applicazione avrebbero generato eccezioni durante la deserializzazione delle versioni precedenti di un tipo con dati mancanti.</span><span class="sxs-lookup"><span data-stu-id="68e67-106">Newer versions of an application would throw exceptions when deserializing older versions of a type with missing data.</span></span>

<span data-ttu-id="68e67-107">La Serializzazione a tolleranza di versione (VTS, Version Tolerant Serialization) è un set di funzionalità introdotto in .NET Framework 2.0 che semplifica, nel tempo, la modifica dei tipi serializzabili.</span><span class="sxs-lookup"><span data-stu-id="68e67-107">Version Tolerant Serialization (VTS) is a set of features introduced in .NET Framework 2.0 that makes it easier, over time, to modify serializable types.</span></span> <span data-ttu-id="68e67-108">In particolare, le funzionalità VTS vengono abilitate per le classi alle quali è stato applicato l'attributo <xref:System.SerializableAttribute>, inclusi i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="68e67-108">Specifically, the VTS features are enabled for classes to which the <xref:System.SerializableAttribute> attribute has been applied, including generic types.</span></span> <span data-ttu-id="68e67-109">VTS rende possibile l'aggiunta di nuovi campi a tali classi senza compromettere la compatibilità con le altre versioni del tipo.</span><span class="sxs-lookup"><span data-stu-id="68e67-109">VTS makes it possible to add new fields to those classes without breaking compatibility with other versions of the type.</span></span> <span data-ttu-id="68e67-110">Per un'applicazione di esempio funzionante, vedere [Esempio di tecnologia di serializzazione indipendente dalla versione](version-tolerant-serialization-technology-sample.md).</span><span class="sxs-lookup"><span data-stu-id="68e67-110">For a working sample application, see [Version Tolerant Serialization Technology Sample](version-tolerant-serialization-technology-sample.md).</span></span>

<span data-ttu-id="68e67-111">Le funzionalità VTS vengono abilitate durante l'utilizzo di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="68e67-111">The VTS features are enabled when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="68e67-112">Inoltre, durante l'utilizzo di <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, sono abilitate tutte le funzionalità salvo la tolleranza di dati estranei.</span><span class="sxs-lookup"><span data-stu-id="68e67-112">Additionally, all features except extraneous data tolerance are also enabled when using the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="68e67-113">Per altre informazioni sull'uso di queste classi per la serializzazione, vedere [Serializzazione binaria](binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="68e67-113">For more information about using these classes for serialization, see [Binary Serialization](binary-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a><span data-ttu-id="68e67-114">Elenco delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="68e67-114">Feature list</span></span>

<span data-ttu-id="68e67-115">Il set di funzionalità comprende quanto segue:</span><span class="sxs-lookup"><span data-stu-id="68e67-115">The set of features includes the following:</span></span>

- <span data-ttu-id="68e67-116">Tolleranza di dati estranei o imprevisti.</span><span class="sxs-lookup"><span data-stu-id="68e67-116">Tolerance of extraneous or unexpected data.</span></span> <span data-ttu-id="68e67-117">Consente a versioni più recenti del tipo di inviare dati alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="68e67-117">This enables newer versions of the type to send data to older versions.</span></span>
- <span data-ttu-id="68e67-118">Tolleranza di dati facoltativi mancanti.</span><span class="sxs-lookup"><span data-stu-id="68e67-118">Tolerance of missing optional data.</span></span> <span data-ttu-id="68e67-119">Consente a versioni precedenti di inviare dati alle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="68e67-119">This enables older versions to send data to newer versions.</span></span>
- <span data-ttu-id="68e67-120">Callback di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-120">Serialization callbacks.</span></span> <span data-ttu-id="68e67-121">Consente l'impostazione intelligente del valore predefinito nei casi in cui dei dati siano mancanti.</span><span class="sxs-lookup"><span data-stu-id="68e67-121">This enables intelligent default value setting in cases where data is missing.</span></span>

<span data-ttu-id="68e67-122">In aggiunta, è presente una funzionalità che consente di dichiarare l'aggiunta di un nuovo campo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="68e67-122">In addition, there is a feature for declaring when a new optional field has been added.</span></span> <span data-ttu-id="68e67-123">Questa è la proprietà <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> dell'attributo <xref:System.Runtime.Serialization.OptionalFieldAttribute>.</span><span class="sxs-lookup"><span data-stu-id="68e67-123">This is the <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> property of the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute.</span></span>

<span data-ttu-id="68e67-124">Queste funzionalità sono descritte più dettagliatamente nelle sezioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="68e67-124">These features are discussed in greater detail in the following sections.</span></span>

### <a name="tolerance-of-extraneous-or-unexpected-data"></a><span data-ttu-id="68e67-125">Tolleranza di dati estranei o imprevisti</span><span class="sxs-lookup"><span data-stu-id="68e67-125">Tolerance of extraneous or unexpected data</span></span>

<span data-ttu-id="68e67-126">In passato, durante la serializzazione, la presenza di dati estranei o imprevisti generava eccezioni.</span><span class="sxs-lookup"><span data-stu-id="68e67-126">In the past, during deserialization, any extraneous or unexpected data caused exceptions to be thrown.</span></span> <span data-ttu-id="68e67-127">Con VTS, nella stessa situazione, eventuali dati estranei o imprevisti vengono ignorati piuttosto che generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="68e67-127">With VTS, in the same situation, any extraneous or unexpected data is ignored instead of causing exceptions to be thrown.</span></span> <span data-ttu-id="68e67-128">Ciò consente alle applicazioni che utilizzano versioni più recenti di un tipo (ovvero una versione che include più campi) di inviare informazioni alle applicazioni che prevedono versioni precedenti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="68e67-128">This enables applications that use newer versions of a type (that is, a version that includes more fields) to send information to applications that expect older versions of the same type.</span></span>

<span data-ttu-id="68e67-129">Nell'esempio riportato di seguito, i dati aggiuntivi contenuti in `CountryField` della versione 2.0 della classe `Address` vengono ignorati nel momento in cui un'applicazione precedente deserializza la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="68e67-129">In the following example, the extra data contained in the `CountryField` of version 2.0 of the `Address` class is ignored when an older application deserializes the newer version.</span></span>

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

### <a name="tolerance-of-missing-data"></a><span data-ttu-id="68e67-130">Tolleranza di dati mancanti</span><span class="sxs-lookup"><span data-stu-id="68e67-130">Tolerance of missing data</span></span>

<span data-ttu-id="68e67-131">I campi possono essere contrassegnati come facoltativi applicando ad essi l'attributo <xref:System.Runtime.Serialization.OptionalFieldAttribute>.</span><span class="sxs-lookup"><span data-stu-id="68e67-131">Fields can be marked as optional by applying the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to them.</span></span> <span data-ttu-id="68e67-132">Durante la deserializzazione, se i dati facoltativi risultano mancanti, il motore di serializzazione ignora tale assenza e non genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="68e67-132">During deserialization, if the optional data is missing, the serialization engine ignores the absence and does not throw an exception.</span></span> <span data-ttu-id="68e67-133">In tal modo, le applicazioni che prevedono versioni precedenti di un tipo, possono inviare dati ad applicazioni che prevedono versioni più recenti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="68e67-133">Thus, applications that expect older versions of a type can send data to applications that expect newer versions of the same type.</span></span>

<span data-ttu-id="68e67-134">Nell'esempio riportato di seguito viene mostrata la versione 2.0 della classe `Address` con il campo `CountryField` contrassegnato come facoltativo.</span><span class="sxs-lookup"><span data-stu-id="68e67-134">The following example shows version 2.0 of the `Address` class with the `CountryField` field marked as optional.</span></span> <span data-ttu-id="68e67-135">Se un'applicazione precedente invia la versione 1 a un'applicazione più recente che prevede la versione 2.0, l'assenza dei dati viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="68e67-135">If an older application sends version 1 to a newer application that expects version 2.0, the absence of the data is ignored.</span></span>

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
  
### <a name="serialization-callbacks"></a><span data-ttu-id="68e67-136">Callback di serializzazione</span><span class="sxs-lookup"><span data-stu-id="68e67-136">Serialization callbacks</span></span>

<span data-ttu-id="68e67-137">I callback di serializzazione rappresentano un meccanismo che fornisce hook nel processo di serializzazione/deserializzazione in quattro punti.</span><span class="sxs-lookup"><span data-stu-id="68e67-137">Serialization callbacks are a mechanism that provides hooks into the serialization/deserialization process at four points.</span></span>

|<span data-ttu-id="68e67-138">Attributo</span><span class="sxs-lookup"><span data-stu-id="68e67-138">Attribute</span></span>|<span data-ttu-id="68e67-139">Quando viene chiamato il metodo associato</span><span class="sxs-lookup"><span data-stu-id="68e67-139">When the Associated Method is Called</span></span>|<span data-ttu-id="68e67-140">Utilizzo tipico</span><span class="sxs-lookup"><span data-stu-id="68e67-140">Typical Use</span></span>|
|---------------|------------------------------------------|-----------------|
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="68e67-141">Prima della deserializzazione.\*</span><span class="sxs-lookup"><span data-stu-id="68e67-141">Before deserialization.\*</span></span>|<span data-ttu-id="68e67-142">Inizializzare i valori predefiniti per i campi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="68e67-142">Initialize default values for optional fields.</span></span>|
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="68e67-143">Dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-143">After deserialization.</span></span>|<span data-ttu-id="68e67-144">Correggere i valori dei campi facoltativi in base al contenuto di altri campi.</span><span class="sxs-lookup"><span data-stu-id="68e67-144">Fix optional field values based on contents of other fields.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="68e67-145">Prima della serializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-145">Before serialization.</span></span>|<span data-ttu-id="68e67-146">Preparare per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-146">Prepare for serialization.</span></span> <span data-ttu-id="68e67-147">Ad esempio, la creazione di strutture di dati facoltativi.</span><span class="sxs-lookup"><span data-stu-id="68e67-147">For example, create optional data structures.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="68e67-148">Dopo la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-148">After serialization.</span></span>|<span data-ttu-id="68e67-149">Registrare gli eventi di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-149">Log serialization events.</span></span>|

 <span data-ttu-id="68e67-150">\* Questo callback viene richiamato prima del costruttore di deserializzazione, se presente.</span><span class="sxs-lookup"><span data-stu-id="68e67-150">\* This callback is invoked before the deserialization constructor, if one is present.</span></span>

#### <a name="using-callbacks"></a><span data-ttu-id="68e67-151">Uso dei callback</span><span class="sxs-lookup"><span data-stu-id="68e67-151">Using callbacks</span></span>

<span data-ttu-id="68e67-152">Per utilizzare i callback, applicare l'attributo appropriato a un metodo che accetta un parametro <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="68e67-152">To use callbacks, apply the appropriate attribute to a method that accepts a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span> <span data-ttu-id="68e67-153">È possibile contrassegnare solo uno metodo per classe con ciascuno di questi attributi.</span><span class="sxs-lookup"><span data-stu-id="68e67-153">Only one method per class can be marked with each of these attributes.</span></span> <span data-ttu-id="68e67-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="68e67-154">For example:</span></span>

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

<span data-ttu-id="68e67-155">L'utilizzo di questi metodi è destinato al controllo la versione.</span><span class="sxs-lookup"><span data-stu-id="68e67-155">The intended use of these methods is for versioning.</span></span> <span data-ttu-id="68e67-156">Durante la deserializzazione, un campo facoltativo potrebbe non essere inizializzato correttamente nel caso in cui i dati del campo risultino mancanti.</span><span class="sxs-lookup"><span data-stu-id="68e67-156">During deserialization, an optional field may not be correctly initialized if the data for the field is missing.</span></span> <span data-ttu-id="68e67-157">Ciò può essere corretto creando il metodo che assegna il valore appropriato e quindi applicando l'attributo **OnDeserializingAttribute** o **OnDeserializedAttribute** al metodo.</span><span class="sxs-lookup"><span data-stu-id="68e67-157">This can be corrected by creating the method that assigns the correct value, then applying either the **OnDeserializingAttribute** or **OnDeserializedAttribute** attribute to the method.</span></span>

<span data-ttu-id="68e67-158">Nell'esempio riportato di seguito, viene mostrato il metodo nel contesto di un tipo.</span><span class="sxs-lookup"><span data-stu-id="68e67-158">The following example shows the method in the context of a type.</span></span> <span data-ttu-id="68e67-159">Se una versione precedente di un'applicazione invia un'istanza della classe `Address` a una versione più recente dell'applicazione, i dati del campo `CountryField` risulteranno mancanti.</span><span class="sxs-lookup"><span data-stu-id="68e67-159">If an earlier version of an application sends an instance of the `Address` class to a later version of the application, the `CountryField` field data will be missing.</span></span> <span data-ttu-id="68e67-160">Ma dopo la deserializzazione, il campo verrà impostato su un valore predefinito "Japan".</span><span class="sxs-lookup"><span data-stu-id="68e67-160">But after deserialization, the field will be set to a default value "Japan".</span></span>

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

## <a name="the-versionadded-property"></a><span data-ttu-id="68e67-161">Proprietà VersionAdded</span><span class="sxs-lookup"><span data-stu-id="68e67-161">The VersionAdded property</span></span>

<span data-ttu-id="68e67-162">L'oggetto **OptionalFieldAttribute** ha la proprietà **VersionAdded**.</span><span class="sxs-lookup"><span data-stu-id="68e67-162">The **OptionalFieldAttribute** has the **VersionAdded** property.</span></span> <span data-ttu-id="68e67-163">In .NET Framework versione 2.0 tale proprietà non viene usata.</span><span class="sxs-lookup"><span data-stu-id="68e67-163">In version 2.0 of the .NET Framework, this isn't used.</span></span> <span data-ttu-id="68e67-164">È tuttavia importante impostare correttamente questa proprietà in modo da essere certi che il tipo sia compatibile con i motori di serializzazione futuri.</span><span class="sxs-lookup"><span data-stu-id="68e67-164">However, it's important to set this property correctly to ensure that the type will be compatible with future serialization engines.</span></span>

<span data-ttu-id="68e67-165">La proprietà indica quale versione di un tipo di un determinato campo è stata aggiunta.</span><span class="sxs-lookup"><span data-stu-id="68e67-165">The property indicates which version of a type a given field has been added.</span></span> <span data-ttu-id="68e67-166">È necessario che venga incrementato esattamente di uno (a partire da 2) ogni volta che viene modificato il tipo, come mostra l'esempio riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="68e67-166">It should be incremented by exactly one (starting at 2) every time the type is modified, as shown in the following example:</span></span>

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

## <a name="serializationbinder"></a><span data-ttu-id="68e67-167">SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="68e67-167">SerializationBinder</span></span>

<span data-ttu-id="68e67-168">In alcuni casi potrebbe essere necessario controllare le classi da serializzare e deserializzare ad esempio perché sono richieste versioni diverse della classe sul server e sul client.</span><span class="sxs-lookup"><span data-stu-id="68e67-168">Some users may need to control which class to serialize and deserialize because a different version of the class is required on the server and client.</span></span> <span data-ttu-id="68e67-169"><xref:System.Runtime.Serialization.SerializationBinder> è una classe astratta usata per controllare i tipi effettivi usati durante la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="68e67-169"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="68e67-170">Per utilizzare questa classe, derivare una classe da <xref:System.Runtime.Serialization.SerializationBinder> ed eseguire l'override dei metodi <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> e <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>,</span><span class="sxs-lookup"><span data-stu-id="68e67-170">To use this class, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> methods.</span></span> <span data-ttu-id="68e67-171">Per altre informazioni, vedere [controllo della serializzazione e deserializzazione con SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span><span class="sxs-lookup"><span data-stu-id="68e67-171">For more information, see [Controlling Serialization and Deserialization with SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span></span>

## <a name="best-practices"></a><span data-ttu-id="68e67-172">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="68e67-172">Best practices</span></span>

<span data-ttu-id="68e67-173">Per essere certi del comportamento corretto del controllo della versione, attenersi a queste regole durante la modifica di un tipo da una versione a un'altra:</span><span class="sxs-lookup"><span data-stu-id="68e67-173">To ensure proper versioning behavior, follow these rules when modifying a type from version to version:</span></span>

- <span data-ttu-id="68e67-174">Non rimuovere mai un campo serializzato.</span><span class="sxs-lookup"><span data-stu-id="68e67-174">Never remove a serialized field.</span></span>
- <span data-ttu-id="68e67-175">Non applicare mai l'attributo <xref:System.NonSerializedAttribute> a un campo se l'attributo non è stato applicato al campo nella versione precedente.</span><span class="sxs-lookup"><span data-stu-id="68e67-175">Never apply the <xref:System.NonSerializedAttribute> attribute to a field if the attribute was not applied to the field in the previous version.</span></span>
- <span data-ttu-id="68e67-176">Non modificare mai il nome o il tipo di un campo serializzato.</span><span class="sxs-lookup"><span data-stu-id="68e67-176">Never change the name or the type of a serialized field.</span></span>
- <span data-ttu-id="68e67-177">Quando si aggiunge un nuovo campo serializzato, applicare l'attributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="68e67-177">When adding a new serialized field, apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="68e67-178">Quando si rimuove un attributo **NonSerializedAttribute** da un campo (non serializzabile in una versione precedente), applicare l'attributo **OptionalFieldAttribute**.</span><span class="sxs-lookup"><span data-stu-id="68e67-178">When removing a **NonSerializedAttribute** attribute from a field (that was not serializable in a previous version), apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="68e67-179">Per tutti i campi facoltativi, impostare valori predefiniti significativi usando callback di serializzazione, a meno che non risultino accettabili 0 o **Null** come valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="68e67-179">For all optional fields, set meaningful defaults using the serialization callbacks unless 0 or **null** as defaults are acceptable.</span></span>

<span data-ttu-id="68e67-180">Per essere certi che un tipo sia compatibile con i motori di serializzazione futuri, seguire le linee guida riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="68e67-180">To ensure that a type will be compatible with future serialization engines, follow these guidelines:</span></span>

- <span data-ttu-id="68e67-181">Impostare sempre la proprietà **VersionAdded** sull'attributo **OptionalFieldAttribute** in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="68e67-181">Always set the **VersionAdded** property on the **OptionalFieldAttribute** attribute correctly.</span></span>
- <span data-ttu-id="68e67-182">Evitare controlli di versione sottoposti a branching.</span><span class="sxs-lookup"><span data-stu-id="68e67-182">Avoid branched versioning.</span></span>

## <a name="see-also"></a><span data-ttu-id="68e67-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68e67-183">See also</span></span>

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
- [<span data-ttu-id="68e67-184">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="68e67-184">Binary Serialization</span></span>](binary-serialization.md)
