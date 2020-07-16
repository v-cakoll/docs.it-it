---
title: Linee guida sulla sicurezza di DataSet e DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: f78b52ede4ec76599d761e5188f39c3e9dae2a4f
ms.sourcegitcommit: 98548968e89739a37625e72ddbd535fe1e11121e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "86405292"
---
# <a name="dataset-and-datatable-security-guidance"></a><span data-ttu-id="98fbf-102">Linee guida sulla sicurezza di DataSet e DataTable</span><span class="sxs-lookup"><span data-stu-id="98fbf-102">DataSet and DataTable security guidance</span></span>

<span data-ttu-id="98fbf-103">Questo articolo si applica a:</span><span class="sxs-lookup"><span data-stu-id="98fbf-103">This article applies to:</span></span>

* <span data-ttu-id="98fbf-104">.NET Framework (tutte le versioni)</span><span class="sxs-lookup"><span data-stu-id="98fbf-104">.NET Framework (all versions)</span></span>
* <span data-ttu-id="98fbf-105">.NET Core e versioni successive</span><span class="sxs-lookup"><span data-stu-id="98fbf-105">.NET Core and later</span></span>
* <span data-ttu-id="98fbf-106">.NET 5,0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="98fbf-106">.NET 5.0 and later</span></span>

<span data-ttu-id="98fbf-107">I tipi [DataSet](/dotnet/api/system.data.dataset) e [DataTable](/dotnet/api/system.data.datatable) sono componenti .NET legacy che consentono di rappresentare i set di dati come oggetti gestiti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-107">The [DataSet](/dotnet/api/system.data.dataset) and [DataTable](/dotnet/api/system.data.datatable) types are legacy .NET components that allow representing data sets as managed objects.</span></span> <span data-ttu-id="98fbf-108">Questi componenti sono stati introdotti in .NET 1,0 come parte dell' [infrastruttura ADO.NET](/dotnet/framework/data/adonet/dataset-datatable-dataview/)originale.</span><span class="sxs-lookup"><span data-stu-id="98fbf-108">These components were introduced in .NET 1.0 as part of the original [ADO.NET infrastructure](/dotnet/framework/data/adonet/dataset-datatable-dataview/).</span></span> <span data-ttu-id="98fbf-109">L'obiettivo era quello di fornire una visualizzazione gestita su un set di dati relazionale, astraendondo se l'origine sottostante dei dati fosse XML, SQL o un'altra tecnologia.</span><span class="sxs-lookup"><span data-stu-id="98fbf-109">Their goal was to provide a managed view over a relational data set, abstracting away whether the underlying source of the data was XML, SQL, or another technology.</span></span>

<span data-ttu-id="98fbf-110">Per ulteriori informazioni su ADO.NET, inclusi i paradigmi di visualizzazione dati più moderni, vedere [la documentazione di ADO.NET](/dotnet/framework/data/adonet/).</span><span class="sxs-lookup"><span data-stu-id="98fbf-110">For more information on ADO.NET, including more modern data view paradigms, see [the ADO.NET documentation](/dotnet/framework/data/adonet/).</span></span>

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a><span data-ttu-id="98fbf-111">Restrizioni predefinite per la deserializzazione di un DataSet o DataTable da XML</span><span class="sxs-lookup"><span data-stu-id="98fbf-111">Default restrictions when deserializing a DataSet or DataTable from XML</span></span>

<span data-ttu-id="98fbf-112">In tutte le versioni supportate di .NET Framework, .NET Core e .NET `DataSet` e si `DataTable` inseriscono le restrizioni seguenti sui tipi di oggetti che possono essere presenti nei dati deserializzati.</span><span class="sxs-lookup"><span data-stu-id="98fbf-112">On all supported versions of .NET Framework, .NET Core, and .NET, `DataSet` and `DataTable` place the following restrictions on what types of objects may be present in the deserialized data.</span></span> <span data-ttu-id="98fbf-113">Per impostazione predefinita, questo elenco è limitato a:</span><span class="sxs-lookup"><span data-stu-id="98fbf-113">By default, this list is restricted to:</span></span>

* <span data-ttu-id="98fbf-114">Primitive e equivalenti primitivi: `bool` ,, `char` `sbyte` , `byte` , `short` , `ushort` , `int` , `uint` , `long` , `ulong` , `float` , `double` , `decimal` , `DateTime` , `DateTimeOffset` , `TimeSpan` , `string` ,,,,, `Guid` `SqlBinary` `SqlBoolean` `SqlByte` `SqlBytes` , `SqlChars` , `SqlDateTime` , `SqlDecimal` , `SqlDouble` , `SqlGuid` , `SqlInt16` , `SqlInt32` , `SqlInt64` , `SqlMoney` , `SqlSingle` e `SqlString` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-114">Primitives and primitive equivalents: `bool`, `char`, `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `DateTime`, `DateTimeOffset`, `TimeSpan`, `string`, `Guid`, `SqlBinary`, `SqlBoolean`, `SqlByte`, `SqlBytes`, `SqlChars`, `SqlDateTime`, `SqlDecimal`, `SqlDouble`, `SqlGuid`, `SqlInt16`, `SqlInt32`, `SqlInt64`, `SqlMoney`, `SqlSingle`, and `SqlString`.</span></span>
* <span data-ttu-id="98fbf-115">Tipi non primitivi usati comunemente: `Type` , `Uri` e `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-115">Commonly used non-primitives: `Type`, `Uri`, and `BigInteger`.</span></span>
* <span data-ttu-id="98fbf-116">Tipi di _sistema. Drawing_ di uso comune: `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` e `SizeF` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-116">Commonly used _System.Drawing_ types: `Color`, `Point`, `PointF`, `Rectangle`, `RectangleF`, `Size`, and `SizeF`.</span></span>
* <span data-ttu-id="98fbf-117">`Enum`tipi.</span><span class="sxs-lookup"><span data-stu-id="98fbf-117">`Enum` types.</span></span>
* <span data-ttu-id="98fbf-118">Matrici ed elenchi dei tipi precedenti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-118">Arrays and lists of the above types.</span></span>

<span data-ttu-id="98fbf-119">Se i dati XML in arrivo contengono un oggetto il cui tipo non è presente nell'elenco:</span><span class="sxs-lookup"><span data-stu-id="98fbf-119">If the incoming XML data contains an object whose type is not in this list:</span></span>

* <span data-ttu-id="98fbf-120">Viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="98fbf-120">An exception is thrown.</span></span>
* <span data-ttu-id="98fbf-121">Operazione di deserializzazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="98fbf-121">The deserialization operation fails.</span></span>

<span data-ttu-id="98fbf-122">Quando si carica il codice XML in un'istanza esistente di `DataSet` o `DataTable` , vengono prese in considerazione anche le definizioni delle colonne esistenti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-122">When loading XML into an existing `DataSet` or `DataTable` instance, the existing column definitions are also taken into account.</span></span> <span data-ttu-id="98fbf-123">Se la tabella contiene già una definizione di colonna di un tipo personalizzato, tale tipo viene temporaneamente aggiunto all'elenco Consenti per la durata dell'operazione di deserializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="98fbf-123">If the table already contains a column definition of a custom type, that type is temporarily added to the allow list for the duration of the XML deserialization operation.</span></span>

```cs
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

<span data-ttu-id="98fbf-124">Le restrizioni relative ai tipi di oggetto si applicano anche quando `XmlSerializer` si usa per deserializzare un'istanza di `DataSet` o `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-124">The object type restrictions also apply when using `XmlSerializer` to deserialize an instance of `DataSet` or `DataTable`.</span></span> <span data-ttu-id="98fbf-125">Tuttavia, potrebbero non essere applicabili quando si utilizza `BinaryFormatter` per deserializzare un'istanza di `DataSet` o `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-125">However, they may not apply when using `BinaryFormatter` to deserialize an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="98fbf-126">Le restrizioni del tipo di oggetto non si applicano quando `DataAdapter.Fill` si utilizza, ad esempio quando un' `DataTable` istanza viene popolata direttamente da un database senza utilizzare le API di deserializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="98fbf-126">The object type restrictions don't apply when using `DataAdapter.Fill`, such as when a `DataTable` instance is populated directly from a database without using the XML deserialization APIs.</span></span>

### <a name="extend-the-list-of-allowed-types"></a><span data-ttu-id="98fbf-127">Estendere l'elenco dei tipi consentiti</span><span class="sxs-lookup"><span data-stu-id="98fbf-127">Extend the list of allowed types</span></span>

<span data-ttu-id="98fbf-128">Un'app può estendere l'elenco dei tipi consentiti per includere tipi personalizzati oltre ai tipi incorporati elencati sopra.</span><span class="sxs-lookup"><span data-stu-id="98fbf-128">An app can extend the allowed types list to include custom types in addition to the built-in types listed above.</span></span> <span data-ttu-id="98fbf-129">Se si estende l'elenco dei tipi consentiti, la modifica influiscono su _tutte_ le `DataSet` istanze di e `DataTable` all'interno dell'app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-129">If extending the allowed types list, the change affects _all_ `DataSet` and `DataTable` instances within the app.</span></span> <span data-ttu-id="98fbf-130">I tipi non possono essere rimossi dall'elenco dei tipi consentiti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-130">Types cannot be removed from the built-in allowed types list.</span></span>

#### <a name="extend-through-configuration-net-framework-40---48"></a><span data-ttu-id="98fbf-131">Estendi tramite configurazione (.NET Framework 4,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="98fbf-131">Extend through configuration (.NET Framework 4.0 - 4.8)</span></span>

<span data-ttu-id="98fbf-132">_App.config_ può essere utilizzato per estendere l'elenco dei tipi consentiti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-132">_App.config_ can be used to extend the allowed types list.</span></span> <span data-ttu-id="98fbf-133">Per estendere l'elenco dei tipi consentiti:</span><span class="sxs-lookup"><span data-stu-id="98fbf-133">To extend the allowed types list:</span></span>

* <span data-ttu-id="98fbf-134">Usare l' `<configSections>` elemento per aggiungere un riferimento alla sezione di configurazione _System. Data_ .</span><span class="sxs-lookup"><span data-stu-id="98fbf-134">Use the `<configSections>` element to add a reference to the _System.Data_ configuration section.</span></span>
* <span data-ttu-id="98fbf-135">Consente `<system.data.dataset.serialization>` / `<allowedTypes>` di specificare tipi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="98fbf-135">Use `<system.data.dataset.serialization>`/`<allowedTypes>` to specify additional types.</span></span>

<span data-ttu-id="98fbf-136">Ogni `<add>` elemento deve specificare un solo tipo utilizzando il relativo nome di tipo completo di assembly.</span><span class="sxs-lookup"><span data-stu-id="98fbf-136">Each `<add>` element must specify only one type by using its assembly qualified type name.</span></span> <span data-ttu-id="98fbf-137">Per aggiungere altri tipi all'elenco dei tipi consentiti, usare più `<add>` elementi.</span><span class="sxs-lookup"><span data-stu-id="98fbf-137">To add additional types to the allowed types list, use multiple `<add>` elements.</span></span>

<span data-ttu-id="98fbf-138">Nell'esempio seguente viene illustrato come estendere l'elenco dei tipi consentiti aggiungendo il tipo personalizzato `Fabrikam.CustomType` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-138">The following sample shows extending the allowed types list by adding the custom type `Fabrikam.CustomType`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="98fbf-139">Per recuperare il nome completo dell'assembly di un tipo, utilizzare la proprietà [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="98fbf-139">To retrieve the assembly qualified name of a type, use the [Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) property, as demonstrated in the following code.</span></span>

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a><span data-ttu-id="98fbf-140">Estendi tramite configurazione (.NET Framework 2,0-3,5)</span><span class="sxs-lookup"><span data-stu-id="98fbf-140">Extend through configuration (.NET Framework 2.0 - 3.5)</span></span>

<span data-ttu-id="98fbf-141">Se l'app è destinata a .NET Framework 2,0 o 3,5, è comunque possibile usare il meccanismo _App.config_ precedente per estendere l'elenco dei tipi consentiti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-141">If your app targets .NET Framework 2.0 or 3.5, you can still use the above _App.config_ mechanism to extend the allowed types list.</span></span> <span data-ttu-id="98fbf-142">Tuttavia, l' `<configSections>` aspetto dell'elemento sarà leggermente diverso, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-142">However, your `<configSections>` element will look slightly different, as shown in the following code:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a><span data-ttu-id="98fbf-143">Estendi a livello di codice (.NET Framework, .NET Core, .NET 5.0 +)</span><span class="sxs-lookup"><span data-stu-id="98fbf-143">Extend programmatically (.NET Framework, .NET Core, .NET 5.0+)</span></span>

<span data-ttu-id="98fbf-144">L'elenco dei tipi consentiti può anche essere esteso a livello di programmazione usando [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) con il noto Key _System. Data. DataSetDefaultAllowedTypes_, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="98fbf-144">The list of allowed types can also be extended programmatically by using [AppDomain.SetData](/dotnet/api/system.appdomain.setdata) with the well-known key _System.Data.DataSetDefaultAllowedTypes_, as shown in the following code.</span></span>

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

<span data-ttu-id="98fbf-145">Se si utilizza il meccanismo di estensione, il valore associato alla chiave _System. Data. DataSetDefaultAllowedTypes_ deve essere di tipo `Type[]` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-145">If using the extension mechanism, the value associated with the key _System.Data.DataSetDefaultAllowedTypes_ must be of type `Type[]`.</span></span>

<span data-ttu-id="98fbf-146">In .NET Framework, l'elenco dei tipi consentiti può essere esteso sia con _App.config_ che con `AppDomain.SetData` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-146">On .NET Framework, the list of allowed types may be extended both with _App.config_ and `AppDomain.SetData`.</span></span> <span data-ttu-id="98fbf-147">In questo caso `DataSet` e `DataTable` consentirà la deserializzazione di un oggetto come parte dei dati se il relativo tipo è presente in uno degli elenchi.</span><span class="sxs-lookup"><span data-stu-id="98fbf-147">In this case, `DataSet` and `DataTable` will allow an object to be deserialized as part of the data if its type is present in either list.</span></span>

### <a name="run-an-app-in-audit-mode-net-framework"></a><span data-ttu-id="98fbf-148">Eseguire un'app in modalità di controllo (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="98fbf-148">Run an app in audit mode (.NET Framework)</span></span>

<span data-ttu-id="98fbf-149">In .NET Framework `DataSet` e `DataTable` fornire una funzionalità della modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="98fbf-149">In .NET Framework, `DataSet` and `DataTable` provide an audit mode capability.</span></span> <span data-ttu-id="98fbf-150">Quando è abilitata la modalità `DataSet` di controllo, `DataTable` confrontare i tipi di oggetti in ingresso con l'elenco dei tipi consentiti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-150">When audit mode is enabled, `DataSet` and `DataTable` compare the types of incoming objects against the allowed types list.</span></span> <span data-ttu-id="98fbf-151">Tuttavia, se viene visualizzato un oggetto il cui tipo non è consentito, **non** viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="98fbf-151">However, if an object whose type is not allowed is seen, an exception is **not** thrown.</span></span> <span data-ttu-id="98fbf-152">In alternativa `DataSet` , `DataTable` inviare una notifica `TraceListener` a tutte le istanze associate che sono presenti tipi sospetti, consentendo `TraceListener` a di registrare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="98fbf-152">Instead, `DataSet` and `DataTable` notify any attached `TraceListener` instances that a suspicious type is present, allowing the `TraceListener` to log this information.</span></span> <span data-ttu-id="98fbf-153">Non viene generata alcuna eccezione e l'operazione di deserializzazione continua.</span><span class="sxs-lookup"><span data-stu-id="98fbf-153">No exception is thrown and the deserialization operation continues.</span></span>

> [!WARNING]
> <span data-ttu-id="98fbf-154">L'esecuzione di un'app in "modalità di controllo" deve essere solo una misura temporanea utilizzata per il testing.</span><span class="sxs-lookup"><span data-stu-id="98fbf-154">Running an app in "audit mode" should only be a temporary measure used for testing.</span></span> <span data-ttu-id="98fbf-155">Quando la modalità di controllo è abilitata `DataSet` e `DataTable` non applica restrizioni di tipo, che possono introdurre un problema di sicurezza all'interno dell'app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-155">When audit mode is enabled, `DataSet` and `DataTable` do not enforce type restrictions, which can introduce a security hole inside your app.</span></span> <span data-ttu-id="98fbf-156">Per ulteriori informazioni, vedere le sezioni intitolate [rimozione di tutte le restrizioni](#ratr) e la protezione dei tipi [per quanto riguarda l'input non attendibile](#swr).</span><span class="sxs-lookup"><span data-stu-id="98fbf-156">For more information, see the sections titled [Removing all type restrictions](#ratr) and [Safety with regard to untrusted input](#swr).</span></span>

<span data-ttu-id="98fbf-157">La modalità di controllo può essere abilitata tramite _App.config_:</span><span class="sxs-lookup"><span data-stu-id="98fbf-157">Audit mode can be enabled through _App.config_:</span></span>

* <span data-ttu-id="98fbf-158">Per informazioni sul valore appropriato da inserire per l'elemento, vedere la sezione [estensione della configurazione](#etc) in questo documento `<configSections>` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-158">See the [Extending through configuration](#etc) section in this document for information on the proper value to put for the `<configSections>` element.</span></span>
* <span data-ttu-id="98fbf-159">Usare `<allowedTypes auditOnly="true">` per abilitare la modalità di controllo, come illustrato nel markup seguente.</span><span class="sxs-lookup"><span data-stu-id="98fbf-159">Use `<allowedTypes auditOnly="true">` to enable audit mode, as shown in the following markup.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="98fbf-160">Una volta abilitata la modalità di controllo, è possibile usare _App.config_ per connettere la classe preferita `TraceListener` a quella `DataSet` predefinita. `TraceSource.` il nome dell'origine di traccia predefinita è _System. Data. DataSet_.</span><span class="sxs-lookup"><span data-stu-id="98fbf-160">Once audit mode is enabled, you can use _App.config_ to connect your preferred `TraceListener` to the `DataSet` built-in `TraceSource.` The name of the built-in trace source is _System.Data.DataSet_.</span></span> <span data-ttu-id="98fbf-161">Nell'esempio seguente viene illustrata la scrittura di eventi di traccia nella console _e_ in un file di log su disco.</span><span class="sxs-lookup"><span data-stu-id="98fbf-161">The following sample demonstrates writing trace events to the console _and_ to a log file on disk.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

<span data-ttu-id="98fbf-162">Per altre informazioni su `TraceSource` e `TraceListener` , vedere il documento [procedura: usare TraceSource e filtri con i listener di traccia](/dotnet/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners).</span><span class="sxs-lookup"><span data-stu-id="98fbf-162">For more information on `TraceSource` and `TraceListener`, see the document [How to: Use TraceSource and Filters with Trace Listeners](/dotnet/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners).</span></span>

> [!NOTE]
> <span data-ttu-id="98fbf-163">L'esecuzione di un'app in modalità di controllo non è disponibile in .NET Core o in .NET 5,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="98fbf-163">Running an app in audit mode is not available in .NET Core or in .NET 5.0 and later.</span></span>

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a><span data-ttu-id="98fbf-164">Rimuovi tutte le restrizioni relative ai tipi</span><span class="sxs-lookup"><span data-stu-id="98fbf-164">Remove all type restrictions</span></span>

<span data-ttu-id="98fbf-165">Se un'app deve rimuovere tutte le restrizioni di limitazione dei tipi da `DataSet` e `DataTable` :</span><span class="sxs-lookup"><span data-stu-id="98fbf-165">If an app must remove all type limiting restrictions from `DataSet` and `DataTable`:</span></span>

* <span data-ttu-id="98fbf-166">Sono disponibili diverse opzioni per l'eliminazione delle restrizioni di limitazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="98fbf-166">There are several options to suppress type limiting restrictions.</span></span>
* <span data-ttu-id="98fbf-167">Le opzioni disponibili dipendono dal Framework a cui è destinata l'app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-167">The options available depend on the framework the app targets.</span></span>

> [!WARNING]
> <span data-ttu-id="98fbf-168">La rimozione di tutte le restrizioni del tipo può introdurre un problema di sicurezza all'interno dell'app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-168">Removing all type restrictions can introduce a security hole inside the app.</span></span> <span data-ttu-id="98fbf-169">Quando si usa questo meccanismo, assicurarsi che l'app **non** usi `DataSet` o `DataTable` per leggere input non attendibile.</span><span class="sxs-lookup"><span data-stu-id="98fbf-169">When using this mechanism, ensure the app does **not** use `DataSet` or `DataTable` to read untrusted input.</span></span> <span data-ttu-id="98fbf-170">Per altre informazioni, vedere [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) e la sezione seguente intitolata [Safety per quanto riguarda l'input non attendibile](#swr).</span><span class="sxs-lookup"><span data-stu-id="98fbf-170">For more information, see [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) and the following section titled [Safety with regard to untrusted input](#swr).</span></span>

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a><span data-ttu-id="98fbf-171">Tramite la configurazione di AppContext (.NET Framework 4,6-4,8, .NET Core 2,1 e versioni successive, .NET 5,0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="98fbf-171">Through AppContext configuration (.NET Framework 4.6 - 4.8, .NET Core 2.1 and later, .NET 5.0 and later)</span></span>

<span data-ttu-id="98fbf-172">`AppContext` `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` Se impostata su, l'opzione consente di `true` rimuovere tutte le restrizioni di limitazione dei tipi da `DataSet` e `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-172">The `AppContext` switch, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation`, when set to `true` removes all type limiting restrictions from `DataSet` and `DataTable`.</span></span>

<span data-ttu-id="98fbf-173">In .NET Framework, questa opzione può essere abilitata tramite _App.config_, come illustrato nella configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-173">In .NET Framework, this switch can be enabled via _App.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

<span data-ttu-id="98fbf-174">In ASP.NET l' `<AppContextSwitchOverrides>` elemento non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="98fbf-174">In ASP.NET, the `<AppContextSwitchOverrides>` element is not available.</span></span> <span data-ttu-id="98fbf-175">Al contrario, l'opzione può essere abilitata tramite _Web.config_, come illustrato nella configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-175">Instead, the switch can be enabled via _Web.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="98fbf-176">Per ulteriori informazioni, vedere l' [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) elemento.</span><span class="sxs-lookup"><span data-stu-id="98fbf-176">For more information, see the [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) element.</span></span>

<span data-ttu-id="98fbf-177">In .NET Core, .NET 5 e ASP.NET Core questa impostazione è controllata da _runtimeconfig.json_, come illustrato nel codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-177">In .NET Core, .NET 5, and ASP.NET Core, this setting is controlled by _runtimeconfig.json_, as shown in the following JSON:</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

<span data-ttu-id="98fbf-178">Per ulteriori informazioni, vedere ["impostazioni di configurazione della fase di esecuzione di .NET Core"](/dotnet/core/run-time-config/).</span><span class="sxs-lookup"><span data-stu-id="98fbf-178">For more information, see [".NET Core run-time configuration settings"](/dotnet/core/run-time-config/).</span></span>

<span data-ttu-id="98fbf-179">`AllowArbitraryDataSetTypeInstantiation`è anche possibile impostare a livello di codice tramite [AppContext. seswitch](/dotnet/api/system.appcontext.setswitch) anziché usare un file di configurazione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-179">`AllowArbitraryDataSetTypeInstantiation` can also be set programmatically via [AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) instead of using a configuration file, as shown in the following code:</span></span>

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 <span data-ttu-id="98fbf-180">Se si sceglie l'approccio programmatico precedente, la chiamata a `AppContext.SetSwitch` deve essere eseguita all'inizio dell'avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-180">If you choose the preceding programmatic approach, the call to `AppContext.SetSwitch` should occur early in the apps startup.</span></span>

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a><span data-ttu-id="98fbf-181">Tramite il registro di sistema a livello di computer (.NET Framework 2,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="98fbf-181">Through the machine-wide registry (.NET Framework 2.0 - 4.8)</span></span>

<span data-ttu-id="98fbf-182">Se `AppContext` non è disponibile, i controlli di limitazione dei tipi possono essere disabilitati con il registro di sistema di Windows:</span><span class="sxs-lookup"><span data-stu-id="98fbf-182">If `AppContext` is not available, type limiting checks can be disabled with the Windows registry:</span></span>

* <span data-ttu-id="98fbf-183">Un amministratore deve configurare il registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="98fbf-183">An administrator must configure the registry.</span></span>
* <span data-ttu-id="98fbf-184">L'uso del registro di sistema è una modifica a livello di computer e ha effetto su _tutte le_ app in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="98fbf-184">Using the registry is a machine-wide change and will affect _all_ apps running on the machine.</span></span>

| <span data-ttu-id="98fbf-185">Type</span><span class="sxs-lookup"><span data-stu-id="98fbf-185">Type</span></span>  |  <span data-ttu-id="98fbf-186">valore</span><span class="sxs-lookup"><span data-stu-id="98fbf-186">Value</span></span> |
|---|---|
| <span data-ttu-id="98fbf-187">**Chiave del Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="98fbf-187">**Registry key**</span></span> | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| <span data-ttu-id="98fbf-188">**Nome del valore**</span><span class="sxs-lookup"><span data-stu-id="98fbf-188">**Value name**</span></span> | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| <span data-ttu-id="98fbf-189">**Tipo di valore**</span><span class="sxs-lookup"><span data-stu-id="98fbf-189">**Value type**</span></span> | `REG_SZ` |
| <span data-ttu-id="98fbf-190">**Dati del valore**</span><span class="sxs-lookup"><span data-stu-id="98fbf-190">**Value data**</span></span> | `true` |

<span data-ttu-id="98fbf-191">In un sistema operativo a 64 bit, questo valore deve essere aggiunto sia per la chiave a 64 bit (mostrata in precedenza) sia per la chiave 32 bit.</span><span class="sxs-lookup"><span data-stu-id="98fbf-191">On a 64-bit operating system, this value my need to be added for both the 64-bit key (shown above) and the 32-bit key.</span></span> <span data-ttu-id="98fbf-192">La chiave a 32 bit si trova in `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-192">The 32-bit key is located at `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext`.</span></span>

<span data-ttu-id="98fbf-193">Per ulteriori informazioni sull'utilizzo del registro di sistema per la configurazione di `AppContext` , vedere ["AppContext for Library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span><span class="sxs-lookup"><span data-stu-id="98fbf-193">For more information on using the registry to configure `AppContext`, see ["AppContext for library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span></span>

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a><span data-ttu-id="98fbf-194">Sicurezza per quanto riguarda l'input non attendibile</span><span class="sxs-lookup"><span data-stu-id="98fbf-194">Safety with regard to untrusted input</span></span>

<span data-ttu-id="98fbf-195">Mentre `DataSet` e `DataTable` impongono limitazioni predefinite sui tipi che possono essere presenti durante la deserializzazione dei payload XML __ `DataSet` e `DataTable` sono in generale non sicuri se popolati con input non attendibile.__</span><span class="sxs-lookup"><span data-stu-id="98fbf-195">While `DataSet` and `DataTable` do impose default limitations on the types that are allowed to be present while deserializing XML payloads, __`DataSet` and `DataTable` are in general not safe when populated with untrusted input.__</span></span> <span data-ttu-id="98fbf-196">Di seguito è riportato un elenco non esaustivo dei modi in cui un' `DataSet` istanza di o `DataTable` può leggere un input non attendibile.</span><span class="sxs-lookup"><span data-stu-id="98fbf-196">The following is a non-exhaustive list of ways that a `DataSet` or `DataTable` instance might read untrusted input.</span></span>

* <span data-ttu-id="98fbf-197">Un oggetto `DataAdapter` fa riferimento a un database e il `DataAdapter.Fill` metodo viene utilizzato per popolare un oggetto `DataSet` con il contenuto di una query di database.</span><span class="sxs-lookup"><span data-stu-id="98fbf-197">A `DataAdapter` references a database, and the `DataAdapter.Fill` method is used to populate a `DataSet` with the contents of a database query.</span></span>
* <span data-ttu-id="98fbf-198">Il `DataSet.ReadXml` `DataTable.ReadXml` metodo o viene utilizzato per leggere un file XML contenente le informazioni su colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="98fbf-198">The `DataSet.ReadXml` or `DataTable.ReadXml` method is used to read an XML file containing column and row information.</span></span>
* <span data-ttu-id="98fbf-199">Un' `DataSet` `DataTable` istanza di o viene serializzata come parte di un servizio Web ASP.NET (SOAP) o di un endpoint WCF.</span><span class="sxs-lookup"><span data-stu-id="98fbf-199">A `DataSet` or `DataTable` instance is serialized as part of a ASP.NET (SOAP) web services or WCF endpoint.</span></span>
* <span data-ttu-id="98fbf-200">Un serializzatore, ad esempio, `XmlSerializer` viene utilizzato per deserializzare un' `DataSet` `DataTable` istanza di o da un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="98fbf-200">A serializer such as `XmlSerializer` is used to deserialize a `DataSet` or `DataTable` instance from an XML stream.</span></span>
* <span data-ttu-id="98fbf-201">Un serializzatore, ad esempio, `JsonConvert` viene usato per deserializzare un' `DataSet` istanza di o `DataTable` da un flusso JSON.</span><span class="sxs-lookup"><span data-stu-id="98fbf-201">A serializer such as `JsonConvert` is used to deserialize a `DataSet` or `DataTable` instance from a JSON stream.</span></span> <span data-ttu-id="98fbf-202">`JsonConvert`è un metodo nell' [Newtonsoft.Js](https://www.newtonsoft.com/json) di terze parti popolare nella libreria.</span><span class="sxs-lookup"><span data-stu-id="98fbf-202">`JsonConvert` is a method in the popular third-party [Newtonsoft.Json](https://www.newtonsoft.com/json) library.</span></span>
* <span data-ttu-id="98fbf-203">Un serializzatore, ad esempio, `BinaryFormatter` viene utilizzato per deserializzare un' `DataSet` `DataTable` istanza di o da un flusso di byte non elaborati.</span><span class="sxs-lookup"><span data-stu-id="98fbf-203">A serializer such as `BinaryFormatter` is used to deserialize a `DataSet` or `DataTable` instance from a raw byte stream.</span></span>

<span data-ttu-id="98fbf-204">In questo documento vengono illustrate le considerazioni sulla sicurezza per gli scenari precedenti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-204">This document discusses safety considerations for the preceding scenarios.</span></span>

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a><span data-ttu-id="98fbf-205">Utilizzare `DataAdapter.Fill` per popolare un oggetto `DataSet` da un'origine dati non attendibile</span><span class="sxs-lookup"><span data-stu-id="98fbf-205">Use `DataAdapter.Fill` to populate a `DataSet` from an untrusted data source</span></span>

<span data-ttu-id="98fbf-206">Un' `DataSet` istanza può essere popolata da un oggetto `DataAdapter` usando [il `DataAdapter.Fill` Metodo](/dotnet/api/system.data.common.dataadapter.fill), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="98fbf-206">A `DataSet` instance can be populated from a `DataAdapter` by using [the `DataAdapter.Fill` method](/dotnet/api/system.data.common.dataadapter.fill), as shown in the following example.</span></span>

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

<span data-ttu-id="98fbf-207">L'esempio di codice precedente fa parte di un esempio più ampio rilevato durante il [popolamento di un DataSet da un oggetto DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).</span><span class="sxs-lookup"><span data-stu-id="98fbf-207">(The code sample above is part of a larger sample found at [Populating a DataSet from a DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).)</span></span>

> <span data-ttu-id="98fbf-208">La maggior parte delle app può semplificare e presupporre che il livello di database sia attendibile.</span><span class="sxs-lookup"><span data-stu-id="98fbf-208">Most apps can simplify and assume that their database layer is trusted.</span></span> <span data-ttu-id="98fbf-209">Tuttavia, se si ha la possibilità di [modellare le minacce](https://www.microsoft.com/securityengineering/sdl/threatmodeling) per le app, il modello di minaccia può considerare la presenza di un confine di trust tra l'applicazione (client) e il livello del database (Server).</span><span class="sxs-lookup"><span data-stu-id="98fbf-209">However, if you are in the habit of [threat modeling](https://www.microsoft.com/securityengineering/sdl/threatmodeling) your apps, your threat model may consider there to be a trust boundary between the application (client) and database layer (server).</span></span> <span data-ttu-id="98fbf-210">L'uso dell' [autenticazione reciproca](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) o dell' [autenticazione AAD](/azure/azure-sql/database/authentication-aad-overview) tra client e server è un modo per risolvere i rischi associati a questo.</span><span class="sxs-lookup"><span data-stu-id="98fbf-210">Using [mutual authentication](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) or [AAD authentication](/azure/azure-sql/database/authentication-aad-overview) between client and server is one way to help address the risks associated with this.</span></span> <span data-ttu-id="98fbf-211">Nella parte restante di questa sezione viene illustrato il possibile risultato di un client che si connette a un server non attendibile.</span><span class="sxs-lookup"><span data-stu-id="98fbf-211">The remainder of this section discusses the possible result of a client connecting to an untrusted server.</span></span>

<span data-ttu-id="98fbf-212">Le conseguenze di un riferimento `DataAdapter` a in un'origine dati non attendibile dipendono dall'implementazione di `DataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-212">The consequences of pointing a `DataAdapter` at an untrusted data source depend on the implementation of the `DataAdapter` itself.</span></span>

### <a name="sqldataadapter"></a><span data-ttu-id="98fbf-213">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="98fbf-213">SqlDataAdapter</span></span>

<span data-ttu-id="98fbf-214">Per il tipo incorporato [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), il riferimento a un'origine dati non attendibile può causare un attacco Denial of Service (DOS).</span><span class="sxs-lookup"><span data-stu-id="98fbf-214">For the built-in type [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), referencing an untrusted data source could result in a denial of service (DoS) attack.</span></span> <span data-ttu-id="98fbf-215">L'attacco DoS potrebbe causare la mancata risposta o l'arresto anomalo dell'app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-215">The DoS attack could result in the app becoming unresponsive or crashing.</span></span> <span data-ttu-id="98fbf-216">Se un utente malintenzionato può creare una DLL insieme all'app, potrebbe anche essere in grado di eseguire l'esecuzione del codice locale.</span><span class="sxs-lookup"><span data-stu-id="98fbf-216">If an attacker can plant a DLL alongside the app, they may also be able to achieve local code execution.</span></span>

### <a name="other-dataadapter-types"></a><span data-ttu-id="98fbf-217">Altri tipi DataAdapter</span><span class="sxs-lookup"><span data-stu-id="98fbf-217">Other DataAdapter types</span></span>

<span data-ttu-id="98fbf-218">Le implementazioni di terze parti `DataAdapter` devono eseguire valutazioni proprie sulle garanzie di sicurezza fornite in presenza di input non attendibili.</span><span class="sxs-lookup"><span data-stu-id="98fbf-218">Third-party `DataAdapter` implementations must make their own assessments about what security guarantees they provide in the face of untrusted inputs.</span></span> <span data-ttu-id="98fbf-219">.NET non è in grado di garantire garanzie di sicurezza relative a queste implementazioni.</span><span class="sxs-lookup"><span data-stu-id="98fbf-219">.NET cannot make any safety guarantees regarding these implementations.</span></span>

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a><span data-ttu-id="98fbf-220">DataSet. ReadXml e DataTable. ReadXml</span><span class="sxs-lookup"><span data-stu-id="98fbf-220">DataSet.ReadXml and DataTable.ReadXml</span></span>

<span data-ttu-id="98fbf-221">I `DataSet.ReadXml` `DataTable.ReadXml` metodi e non sono sicuri se usati con input non attendibile.</span><span class="sxs-lookup"><span data-stu-id="98fbf-221">The `DataSet.ReadXml` and `DataTable.ReadXml` methods are not safe when used with untrusted input.</span></span> <span data-ttu-id="98fbf-222">È consigliabile che i consumer considerino invece una delle alternative descritte più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="98fbf-222">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this document.</span></span>

<span data-ttu-id="98fbf-223">Le implementazioni di `DataSet.ReadXml` e `DataTable.ReadXml` sono state create originariamente prima che le vulnerabilità di serializzazione fossero una categoria di minacce ben riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="98fbf-223">The implementations of `DataSet.ReadXml` and `DataTable.ReadXml` were originally created before serialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="98fbf-224">Di conseguenza, il codice non segue le procedure di sicurezza consigliate correnti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-224">As a result, the code does not follow current security best practices.</span></span> <span data-ttu-id="98fbf-225">Queste API possono essere usate come vettori per gli utenti malintenzionati per eseguire attacchi DoS contro le app Web.</span><span class="sxs-lookup"><span data-stu-id="98fbf-225">These APIs can be used as vectors for attackers to perform DoS attacks against web apps.</span></span> <span data-ttu-id="98fbf-226">Questi attacchi potrebbero rendere il servizio Web non risponde o causare una chiusura imprevista del processo.</span><span class="sxs-lookup"><span data-stu-id="98fbf-226">These attacks might render the web service unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="98fbf-227">Il Framework non fornisce mitigazioni per queste categorie di attacco e .NET considera questo comportamento "da progettazione".</span><span class="sxs-lookup"><span data-stu-id="98fbf-227">The framework does not provide mitigations for these attack categories and .NET considers this behavior "by design".</span></span>

<span data-ttu-id="98fbf-228">.NET ha rilasciato aggiornamenti della protezione per attenuare alcuni problemi, ad esempio la divulgazione di informazioni o l'esecuzione di codice in modalità remota in `DataSet.ReadXml` e `DataTable.ReadXml` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-228">.NET has released security updates to mitigate some issues such as information disclosure or remote code execution in `DataSet.ReadXml` and `DataTable.ReadXml`.</span></span> <span data-ttu-id="98fbf-229">Gli aggiornamenti della sicurezza di .NET potrebbero non fornire una protezione completa da queste categorie di minacce.</span><span class="sxs-lookup"><span data-stu-id="98fbf-229">The .NET security updates may not provide complete protection against these threat categories.</span></span> <span data-ttu-id="98fbf-230">I consumer devono valutare i singoli scenari e prendere in considerazione la loro potenziale esposizione a questi rischi.</span><span class="sxs-lookup"><span data-stu-id="98fbf-230">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="98fbf-231">Gli utenti devono tenere presente che gli aggiornamenti della sicurezza per queste API possono influisca sulla compatibilità delle applicazioni in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="98fbf-231">Consumers should be aware that security updates to these APIs may impact application compatibility in some situations.</span></span> <span data-ttu-id="98fbf-232">Inoltre, esiste la possibilità che venga individuata una nuova vulnerabilità in queste API per cui .NET non può pubblicare praticamente un aggiornamento della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="98fbf-232">Furthermore, the possibility exists that a novel vulnerability in these APIs will be discovered for which .NET can't practically publish a security update.</span></span>

<span data-ttu-id="98fbf-233">È consigliabile che i consumer di queste API siano:</span><span class="sxs-lookup"><span data-stu-id="98fbf-233">We recommend that consumers of these APIs either:</span></span>

* <span data-ttu-id="98fbf-234">Prendere in considerazione l'uso di una delle alternative descritte più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="98fbf-234">Consider using one of the alternatives outlined later in this document.</span></span>
* <span data-ttu-id="98fbf-235">Eseguire valutazioni dei rischi individuali sulle app.</span><span class="sxs-lookup"><span data-stu-id="98fbf-235">Perform individual risk assessments on their apps.</span></span>

<span data-ttu-id="98fbf-236">È responsabilità dell'utente determinare se usare queste API.</span><span class="sxs-lookup"><span data-stu-id="98fbf-236">It is the consumer's sole responsibility to determine whether to utilize these APIs.</span></span> <span data-ttu-id="98fbf-237">I consumer devono valutare eventuali rischi di sicurezza, tecnici e legali, inclusi i requisiti normativi, che possono accompagnare l'uso di queste API.</span><span class="sxs-lookup"><span data-stu-id="98fbf-237">Consumers should assess any security, technical, and legal risks, including regulatory requirements, that may accompany using these APIs.</span></span>

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a><span data-ttu-id="98fbf-238">DataSet e DataTable tramite i servizi Web ASP.NET o WCF</span><span class="sxs-lookup"><span data-stu-id="98fbf-238">DataSet and DataTable via ASP.NET web services or WCF</span></span>

<span data-ttu-id="98fbf-239">È possibile accettare un' `DataSet` `DataTable` istanza di o in un servizio Web ASP.NET (SOAP), come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-239">It is possible to accept a `DataSet` or a `DataTable` instance in an ASP.NET (SOAP) web service, as demonstrated in the following code:</span></span>

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

<span data-ttu-id="98fbf-240">Una variante di questa operazione non è accettare `DataSet` o `DataTable` direttamente come parametro, ma accettarla come parte dell'oggetto grafico globale serializzato SOAP, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-240">A variation on this is not to accept `DataSet` or `DataTable` directly as a parameter, but instead to accept it as part of the overall SOAP serialized object graph, as shown in the following code:</span></span>

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="98fbf-241">In alternativa, utilizzare WCF anziché i servizi Web di ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="98fbf-241">Or, using WCF instead of ASP.NET web services:</span></span>

```cs
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="98fbf-242">In tutti questi casi, il modello di minaccia e le garanzie di sicurezza sono gli stessi della [sezione DataSet. ReadXml e DataTable. ReadXml](#dsrdtr).</span><span class="sxs-lookup"><span data-stu-id="98fbf-242">In all of these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr).</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a><span data-ttu-id="98fbf-243">Deserializzare un DataSet o DataTable tramite XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="98fbf-243">Deserialize a DataSet or DataTable via XmlSerializer</span></span>

<span data-ttu-id="98fbf-244">Gli sviluppatori possono utilizzare `XmlSerializer` per deserializzare `DataSet` `DataTable` le istanze di e, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-244">Developers can use `XmlSerializer` to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="98fbf-245">In questi casi, il modello di minaccia e le garanzie di sicurezza sono gli stessi della [sezione DataSet. ReadXml e DataTable. ReadXml](#dsrdtr)</span><span class="sxs-lookup"><span data-stu-id="98fbf-245">In these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr)</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a><span data-ttu-id="98fbf-246">Deserializzare un DataSet o DataTable tramite JsonConvert</span><span class="sxs-lookup"><span data-stu-id="98fbf-246">Deserialize a DataSet or DataTable via JsonConvert</span></span>

<span data-ttu-id="98fbf-247">La popolare libreria Newtonsoft di terze parti [JSON.NET](https://www.newtonsoft.com/json) può essere usata per deserializzare le `DataSet` istanze di e `DataTable` , come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="98fbf-247">The popular third-party Newtonsoft library [JSON.NET](https://www.newtonsoft.com/json) can be used to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="98fbf-248">La deserializzazione di un oggetto `DataSet` o `DataTable` in questo modo da un BLOB JSON non attendibile non è sicura.</span><span class="sxs-lookup"><span data-stu-id="98fbf-248">Deserializing a `DataSet` or `DataTable` in this manner from an untrusted JSON blob is not safe.</span></span> <span data-ttu-id="98fbf-249">Questo modello è vulnerabile a un attacco di tipo Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="98fbf-249">This pattern is vulnerable to a denial of service attack.</span></span> <span data-ttu-id="98fbf-250">Un attacco di questo tipo potrebbe causare l'arresto anomalo dell'app o il rendering non risponde.</span><span class="sxs-lookup"><span data-stu-id="98fbf-250">Such an attack could crash the app or render it unresponsive.</span></span>

> [!NOTE]
> <span data-ttu-id="98fbf-251">Microsoft non garantisce né supporta l'implementazione di librerie di terze parti come _Newtonsoft.Json_.</span><span class="sxs-lookup"><span data-stu-id="98fbf-251">Microsoft does not warrant or support the implementation of third-party libraries like _Newtonsoft.Json_.</span></span> <span data-ttu-id="98fbf-252">Queste informazioni vengono fornite per completezza ed è accurate al momento della stesura di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="98fbf-252">This information is provided for completeness and is accurate as of the time of this writing.</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a><span data-ttu-id="98fbf-253">Deserializzare un DataSet o un DataTable tramite BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="98fbf-253">Deserialize a DataSet or DataTable via BinaryFormatter</span></span>

<span data-ttu-id="98fbf-254">Gli sviluppatori non devono mai usare i `BinaryFormatter` `NetDataContractSerializer` `SoapFormatter` formattatori non ***sicuri*** correlati,, o per deserializzare un' `DataSet` istanza di o `DataTable` da un payload non attendibile:</span><span class="sxs-lookup"><span data-stu-id="98fbf-254">Developers must never use `BinaryFormatter`, `NetDataContractSerializer`, `SoapFormatter`, or related ***unsafe*** formatters to deserialize a `DataSet` or `DataTable` instance from an untrusted payload:</span></span>

* <span data-ttu-id="98fbf-255">Questa operazione è soggetta a un attacco di esecuzione del codice remoto completo.</span><span class="sxs-lookup"><span data-stu-id="98fbf-255">This is susceptible to a full remote code execution attack.</span></span>
* <span data-ttu-id="98fbf-256">L'uso di un oggetto personalizzato `SerializationBinder` non è sufficiente per evitare tale attacco.</span><span class="sxs-lookup"><span data-stu-id="98fbf-256">Using a custom `SerializationBinder` is not sufficient to prevent such an attack.</span></span>

## <a name="safe-replacements"></a><span data-ttu-id="98fbf-257">Sostituzioni sicure</span><span class="sxs-lookup"><span data-stu-id="98fbf-257">Safe replacements</span></span>

<span data-ttu-id="98fbf-258">Per le app che possono:</span><span class="sxs-lookup"><span data-stu-id="98fbf-258">For apps that either:</span></span>

* <span data-ttu-id="98fbf-259">Accettare `DataSet` o `DataTable` tramite un endpoint SOAP. asmx o un endpoint WCF.</span><span class="sxs-lookup"><span data-stu-id="98fbf-259">Accept `DataSet` or `DataTable` through an .asmx SOAP endpoint or a WCF endpoint.</span></span>
* <span data-ttu-id="98fbf-260">Deserializzare i dati non attendibili in un'istanza di `DataSet` o `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="98fbf-260">Deserialize untrusted data into an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="98fbf-261">Prendere in considerazione la sostituzione del modello a oggetti per usare [Entity Framework](/ef).</span><span class="sxs-lookup"><span data-stu-id="98fbf-261">Consider replacing the object model to use [Entity Framework](/ef).</span></span> <span data-ttu-id="98fbf-262">Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="98fbf-262">Entity Framework:</span></span>

* <span data-ttu-id="98fbf-263">È un Framework avanzato, moderno e orientato a oggetti, che può rappresentare dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="98fbf-263">Is a rich, modern, object-oriented framework that can represent relational data.</span></span>
* <span data-ttu-id="98fbf-264">Offre [un ecosistema diversificato](/ef/core/providers/) di provider di database per semplificare la progettazione di query di database tramite i modelli a oggetti Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="98fbf-264">Brings [a diverse ecosystem](/ef/core/providers/) of database providers to make it easy to project database queries via your Entity Framework object models.</span></span>
* <span data-ttu-id="98fbf-265">Offre protezioni predefinite per la deserializzazione dei dati da origini non attendibili.</span><span class="sxs-lookup"><span data-stu-id="98fbf-265">Offers built-in protections when deserializing data from untrusted sources.</span></span>

<span data-ttu-id="98fbf-266">Per le app che usano `.aspx` gli endpoint SOAP, provare a modificare tali endpoint per l'uso di [WCF](/dotnet/framework/wcf/).</span><span class="sxs-lookup"><span data-stu-id="98fbf-266">For apps that use `.aspx` SOAP endpoints, consider changing those endpoints to use [WCF](/dotnet/framework/wcf/).</span></span> <span data-ttu-id="98fbf-267">WCF è una sostituzione più completa per i `.asmx` servizi Web.</span><span class="sxs-lookup"><span data-stu-id="98fbf-267">WCF is a more fully featured replacement for `.asmx` web services.</span></span> <span data-ttu-id="98fbf-268">Gli endpoint WCF [possono essere esposti tramite SOAP](/dotnet/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients) per la compatibilità con i chiamanti esistenti.</span><span class="sxs-lookup"><span data-stu-id="98fbf-268">WCF endpoints [can be exposed via SOAP](/dotnet/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients) for compatibility with existing callers.</span></span>
