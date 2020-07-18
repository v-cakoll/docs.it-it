---
title: Linee guida sulla sicurezza di DataSet e DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: 2fbac625ae0049fc4c363977dc1d3fbcfb376025
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416202"
---
# <a name="dataset-and-datatable-security-guidance"></a>Linee guida sulla sicurezza di DataSet e DataTable

Questo articolo si applica a:

* .NET Framework (tutte le versioni)
* .NET Core e versioni successive
* .NET 5,0 e versioni successive

I tipi [DataSet](/dotnet/api/system.data.dataset) e [DataTable](/dotnet/api/system.data.datatable) sono componenti .NET legacy che consentono di rappresentare i set di dati come oggetti gestiti. Questi componenti sono stati introdotti in .NET 1,0 come parte dell' [infrastruttura ADO.NET](/dotnet/framework/data/adonet/dataset-datatable-dataview/)originale. L'obiettivo era quello di fornire una visualizzazione gestita su un set di dati relazionale, astraendondo se l'origine sottostante dei dati fosse XML, SQL o un'altra tecnologia.

Per ulteriori informazioni su ADO.NET, inclusi i paradigmi di visualizzazione dati più moderni, vedere [la documentazione di ADO.NET](/dotnet/framework/data/adonet/).

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a>Restrizioni predefinite per la deserializzazione di un DataSet o DataTable da XML

In tutte le versioni supportate di .NET Framework, .NET Core e .NET `DataSet` e si `DataTable` inseriscono le restrizioni seguenti sui tipi di oggetti che possono essere presenti nei dati deserializzati. Per impostazione predefinita, questo elenco è limitato a:

* Primitive e equivalenti primitivi: `bool` ,, `char` `sbyte` , `byte` , `short` , `ushort` , `int` , `uint` , `long` , `ulong` , `float` , `double` , `decimal` , `DateTime` , `DateTimeOffset` , `TimeSpan` , `string` ,,,,, `Guid` `SqlBinary` `SqlBoolean` `SqlByte` `SqlBytes` , `SqlChars` , `SqlDateTime` , `SqlDecimal` , `SqlDouble` , `SqlGuid` , `SqlInt16` , `SqlInt32` , `SqlInt64` , `SqlMoney` , `SqlSingle` e `SqlString` .
* Tipi non primitivi usati comunemente: `Type` , `Uri` e `BigInteger` .
* Tipi di _sistema. Drawing_ di uso comune: `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` e `SizeF` .
* `Enum`tipi.
* Matrici ed elenchi dei tipi precedenti.

Se i dati XML in arrivo contengono un oggetto il cui tipo non è presente nell'elenco:

* Viene generata un'eccezione.
* Operazione di deserializzazione non riuscita.

Quando si carica il codice XML in un'istanza esistente di `DataSet` o `DataTable` , vengono prese in considerazione anche le definizioni delle colonne esistenti. Se la tabella contiene già una definizione di colonna di un tipo personalizzato, tale tipo viene temporaneamente aggiunto all'elenco Consenti per la durata dell'operazione di deserializzazione XML.

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

Le restrizioni relative ai tipi di oggetto si applicano anche quando `XmlSerializer` si usa per deserializzare un'istanza di `DataSet` o `DataTable` . Tuttavia, potrebbero non essere applicabili quando si utilizza `BinaryFormatter` per deserializzare un'istanza di `DataSet` o `DataTable` .

Le restrizioni del tipo di oggetto non si applicano quando `DataAdapter.Fill` si utilizza, ad esempio quando un' `DataTable` istanza viene popolata direttamente da un database senza utilizzare le API di deserializzazione XML.

### <a name="extend-the-list-of-allowed-types"></a>Estendere l'elenco dei tipi consentiti

Un'app può estendere l'elenco dei tipi consentiti per includere tipi personalizzati oltre ai tipi incorporati elencati sopra. Se si estende l'elenco dei tipi consentiti, la modifica influiscono su _tutte_ le `DataSet` istanze di e `DataTable` all'interno dell'app. I tipi non possono essere rimossi dall'elenco dei tipi consentiti predefiniti.

#### <a name="extend-through-configuration-net-framework-40---48"></a>Estendi tramite configurazione (.NET Framework 4,0-4,8)

_App.config_ può essere utilizzato per estendere l'elenco dei tipi consentiti. Per estendere l'elenco dei tipi consentiti:

* Usare l' `<configSections>` elemento per aggiungere un riferimento alla sezione di configurazione _System. Data_ .
* Consente `<system.data.dataset.serialization>` / `<allowedTypes>` di specificare tipi aggiuntivi.

Ogni `<add>` elemento deve specificare un solo tipo utilizzando il relativo nome di tipo completo di assembly. Per aggiungere altri tipi all'elenco dei tipi consentiti, usare più `<add>` elementi.

Nell'esempio seguente viene illustrato come estendere l'elenco dei tipi consentiti aggiungendo il tipo personalizzato `Fabrikam.CustomType` .

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

Per recuperare il nome completo dell'assembly di un tipo, utilizzare la proprietà [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , come illustrato nel codice seguente.

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a>Estendi tramite configurazione (.NET Framework 2,0-3,5)

Se l'app è destinata a .NET Framework 2,0 o 3,5, è comunque possibile usare il meccanismo _App.config_ precedente per estendere l'elenco dei tipi consentiti. Tuttavia, l' `<configSections>` aspetto dell'elemento sarà leggermente diverso, come illustrato nel codice seguente:

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

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a>Estendi a livello di codice (.NET Framework, .NET Core, .NET 5.0 +)

L'elenco dei tipi consentiti può anche essere esteso a livello di programmazione usando [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) con il noto Key _System. Data. DataSetDefaultAllowedTypes_, come illustrato nel codice seguente.

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

Se si utilizza il meccanismo di estensione, il valore associato alla chiave _System. Data. DataSetDefaultAllowedTypes_ deve essere di tipo `Type[]` .

In .NET Framework, l'elenco dei tipi consentiti può essere esteso sia con _App.config_ che con `AppDomain.SetData` . In questo caso `DataSet` e `DataTable` consentirà la deserializzazione di un oggetto come parte dei dati se il relativo tipo è presente in uno degli elenchi.

### <a name="run-an-app-in-audit-mode-net-framework"></a>Eseguire un'app in modalità di controllo (.NET Framework)

In .NET Framework `DataSet` e `DataTable` fornire una funzionalità della modalità di controllo. Quando è abilitata la modalità `DataSet` di controllo, `DataTable` confrontare i tipi di oggetti in ingresso con l'elenco dei tipi consentiti. Tuttavia, se viene visualizzato un oggetto il cui tipo non è consentito, **non** viene generata un'eccezione. In alternativa `DataSet` , `DataTable` inviare una notifica `TraceListener` a tutte le istanze associate che sono presenti tipi sospetti, consentendo `TraceListener` a di registrare le informazioni. Non viene generata alcuna eccezione e l'operazione di deserializzazione continua.

> [!WARNING]
> L'esecuzione di un'app in "modalità di controllo" deve essere solo una misura temporanea utilizzata per il testing. Quando la modalità di controllo è abilitata `DataSet` e `DataTable` non applica restrizioni di tipo, che possono introdurre un problema di sicurezza all'interno dell'app. Per ulteriori informazioni, vedere le sezioni intitolate [rimozione di tutte le restrizioni](#ratr) e la protezione dei tipi [per quanto riguarda l'input non attendibile](#swr).

La modalità di controllo può essere abilitata tramite _App.config_:

* Per informazioni sul valore appropriato da inserire per l'elemento, vedere la sezione [estensione della configurazione](#etc) in questo documento `<configSections>` .
* Usare `<allowedTypes auditOnly="true">` per abilitare la modalità di controllo, come illustrato nel markup seguente.

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

Una volta abilitata la modalità di controllo, è possibile usare _App.config_ per connettere la classe preferita `TraceListener` a quella `DataSet` predefinita. `TraceSource.` il nome dell'origine di traccia predefinita è _System. Data. DataSet_. Nell'esempio seguente viene illustrata la scrittura di eventi di traccia nella console _e_ in un file di log su disco.

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

Per altre informazioni su `TraceSource` e `TraceListener` , vedere il documento [procedura: usare TraceSource e filtri con i listener di traccia](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).

> [!NOTE]
> L'esecuzione di un'app in modalità di controllo non è disponibile in .NET Core o in .NET 5,0 e versioni successive.

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a>Rimuovi tutte le restrizioni relative ai tipi

Se un'app deve rimuovere tutte le restrizioni di limitazione dei tipi da `DataSet` e `DataTable` :

* Sono disponibili diverse opzioni per l'eliminazione delle restrizioni di limitazione del tipo.
* Le opzioni disponibili dipendono dal Framework a cui è destinata l'app.

> [!WARNING]
> La rimozione di tutte le restrizioni del tipo può introdurre un problema di sicurezza all'interno dell'app. Quando si usa questo meccanismo, assicurarsi che l'app **non** usi `DataSet` o `DataTable` per leggere input non attendibile. Per altre informazioni, vedere [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) e la sezione seguente intitolata [Safety per quanto riguarda l'input non attendibile](#swr).

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a>Tramite la configurazione di AppContext (.NET Framework 4,6-4,8, .NET Core 2,1 e versioni successive, .NET 5,0 e versioni successive)

`AppContext` `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` Se impostata su, l'opzione consente di `true` rimuovere tutte le restrizioni di limitazione dei tipi da `DataSet` e `DataTable` .

In .NET Framework, questa opzione può essere abilitata tramite _App.config_, come illustrato nella configurazione seguente:

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

In ASP.NET l' `<AppContextSwitchOverrides>` elemento non è disponibile. Al contrario, l'opzione può essere abilitata tramite _Web.config_, come illustrato nella configurazione seguente:

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

Per ulteriori informazioni, vedere l' [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento.

In .NET Core, .NET 5 e ASP.NET Core questa impostazione è controllata da _runtimeconfig.json_, come illustrato nel codice JSON seguente:

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

Per ulteriori informazioni, vedere ["impostazioni di configurazione della fase di esecuzione di .NET Core"](/dotnet/core/run-time-config/).

`AllowArbitraryDataSetTypeInstantiation`è anche possibile impostare a livello di codice tramite [AppContext. seswitch](/dotnet/api/system.appcontext.setswitch) anziché usare un file di configurazione, come illustrato nel codice seguente:

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 Se si sceglie l'approccio programmatico precedente, la chiamata a `AppContext.SetSwitch` deve essere eseguita all'inizio dell'avvio delle app.

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a>Tramite il registro di sistema a livello di computer (.NET Framework 2,0-4,8)

Se `AppContext` non è disponibile, i controlli di limitazione dei tipi possono essere disabilitati con il registro di sistema di Windows:

* Un amministratore deve configurare il registro di sistema.
* L'uso del registro di sistema è una modifica a livello di computer e ha effetto su _tutte le_ app in esecuzione nel computer.

| Type  |  valore |
|---|---|
| **Chiave del Registro di sistema** | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| **Nome del valore** | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| **Tipo di valore** | `REG_SZ` |
| **Dati del valore** | `true` |

In un sistema operativo a 64 bit, questo valore deve essere aggiunto sia per la chiave a 64 bit (mostrata in precedenza) sia per la chiave 32 bit. La chiave a 32 bit si trova in `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .

Per ulteriori informazioni sull'utilizzo del registro di sistema per la configurazione di `AppContext` , vedere ["AppContext for Library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a>Sicurezza per quanto riguarda l'input non attendibile

Mentre `DataSet` e `DataTable` impongono limitazioni predefinite sui tipi che possono essere presenti durante la deserializzazione dei payload XML __ `DataSet` e `DataTable` sono in generale non sicuri se popolati con input non attendibile.__ Di seguito è riportato un elenco non esaustivo dei modi in cui un' `DataSet` istanza di o `DataTable` può leggere un input non attendibile.

* Un oggetto `DataAdapter` fa riferimento a un database e il `DataAdapter.Fill` metodo viene utilizzato per popolare un oggetto `DataSet` con il contenuto di una query di database.
* Il `DataSet.ReadXml` `DataTable.ReadXml` metodo o viene utilizzato per leggere un file XML contenente le informazioni su colonne e righe.
* Un' `DataSet` `DataTable` istanza di o viene serializzata come parte di un servizio Web ASP.NET (SOAP) o di un endpoint WCF.
* Un serializzatore, ad esempio, `XmlSerializer` viene utilizzato per deserializzare un' `DataSet` `DataTable` istanza di o da un flusso XML.
* Un serializzatore, ad esempio, `JsonConvert` viene usato per deserializzare un' `DataSet` istanza di o `DataTable` da un flusso JSON. `JsonConvert`è un metodo nell' [Newtonsoft.Js](https://www.newtonsoft.com/json) di terze parti popolare nella libreria.
* Un serializzatore, ad esempio, `BinaryFormatter` viene utilizzato per deserializzare un' `DataSet` `DataTable` istanza di o da un flusso di byte non elaborati.

In questo documento vengono illustrate le considerazioni sulla sicurezza per gli scenari precedenti.

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a>Utilizzare `DataAdapter.Fill` per popolare un oggetto `DataSet` da un'origine dati non attendibile

Un' `DataSet` istanza può essere popolata da un oggetto `DataAdapter` usando [il `DataAdapter.Fill` Metodo](/dotnet/api/system.data.common.dataadapter.fill), come illustrato nell'esempio seguente.

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

L'esempio di codice precedente fa parte di un esempio più ampio rilevato durante il [popolamento di un DataSet da un oggetto DataAdapter](../populating-a-dataset-from-a-dataadapter.md).

> La maggior parte delle app può semplificare e presupporre che il livello di database sia attendibile. Tuttavia, se si ha la possibilità di [modellare le minacce](https://www.microsoft.com/securityengineering/sdl/threatmodeling) per le app, il modello di minaccia può considerare la presenza di un confine di trust tra l'applicazione (client) e il livello del database (Server). L'uso dell' [autenticazione reciproca](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) o dell' [autenticazione AAD](/azure/azure-sql/database/authentication-aad-overview) tra client e server è un modo per risolvere i rischi associati a questo. Nella parte restante di questa sezione viene illustrato il possibile risultato di un client che si connette a un server non attendibile.

Le conseguenze di un riferimento `DataAdapter` a in un'origine dati non attendibile dipendono dall'implementazione di `DataAdapter` .

### <a name="sqldataadapter"></a>SqlDataAdapter

Per il tipo incorporato [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), il riferimento a un'origine dati non attendibile può causare un attacco Denial of Service (DOS). L'attacco DoS potrebbe causare la mancata risposta o l'arresto anomalo dell'app. Se un utente malintenzionato può creare una DLL insieme all'app, potrebbe anche essere in grado di eseguire l'esecuzione del codice locale.

### <a name="other-dataadapter-types"></a>Altri tipi DataAdapter

Le implementazioni di terze parti `DataAdapter` devono eseguire valutazioni proprie sulle garanzie di sicurezza fornite in presenza di input non attendibili. .NET non è in grado di garantire garanzie di sicurezza relative a queste implementazioni.

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a>DataSet. ReadXml e DataTable. ReadXml

I `DataSet.ReadXml` `DataTable.ReadXml` metodi e non sono sicuri se usati con input non attendibile. È consigliabile che i consumer considerino invece una delle alternative descritte più avanti in questo documento.

Le implementazioni di `DataSet.ReadXml` e `DataTable.ReadXml` sono state create originariamente prima che le vulnerabilità di serializzazione fossero una categoria di minacce ben riconosciuta. Di conseguenza, il codice non segue le procedure di sicurezza consigliate correnti. Queste API possono essere usate come vettori per gli utenti malintenzionati per eseguire attacchi DoS contro le app Web. Questi attacchi potrebbero rendere il servizio Web non risponde o causare una chiusura imprevista del processo. Il Framework non fornisce mitigazioni per queste categorie di attacco e .NET considera questo comportamento "da progettazione".

.NET ha rilasciato aggiornamenti della protezione per attenuare alcuni problemi, ad esempio la divulgazione di informazioni o l'esecuzione di codice in modalità remota in `DataSet.ReadXml` e `DataTable.ReadXml` . Gli aggiornamenti della sicurezza di .NET potrebbero non fornire una protezione completa da queste categorie di minacce. I consumer devono valutare i singoli scenari e prendere in considerazione la loro potenziale esposizione a questi rischi.

Gli utenti devono tenere presente che gli aggiornamenti della sicurezza per queste API possono influisca sulla compatibilità delle applicazioni in alcune situazioni. Inoltre, esiste la possibilità che venga individuata una nuova vulnerabilità in queste API per cui .NET non può pubblicare praticamente un aggiornamento della sicurezza.

È consigliabile che i consumer di queste API siano:

* Prendere in considerazione l'uso di una delle alternative descritte più avanti in questo documento.
* Eseguire valutazioni dei rischi individuali sulle app.

È responsabilità dell'utente determinare se usare queste API. I consumer devono valutare eventuali rischi di sicurezza, tecnici e legali, inclusi i requisiti normativi, che possono accompagnare l'uso di queste API.

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a>DataSet e DataTable tramite i servizi Web ASP.NET o WCF

È possibile accettare un' `DataSet` `DataTable` istanza di o in un servizio Web ASP.NET (SOAP), come illustrato nel codice seguente:

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

Una variante di questa operazione non è accettare `DataSet` o `DataTable` direttamente come parametro, ma accettarla come parte dell'oggetto grafico globale serializzato SOAP, come illustrato nel codice seguente:

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

In alternativa, utilizzare WCF anziché i servizi Web di ASP.NET:

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

In tutti questi casi, il modello di minaccia e le garanzie di sicurezza sono gli stessi della [sezione DataSet. ReadXml e DataTable. ReadXml](#dsrdtr).

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a>Deserializzare un DataSet o DataTable tramite XmlSerializer

Gli sviluppatori possono utilizzare `XmlSerializer` per deserializzare `DataSet` `DataTable` le istanze di e, come illustrato nel codice seguente:

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

In questi casi, il modello di minaccia e le garanzie di sicurezza sono gli stessi della [sezione DataSet. ReadXml e DataTable. ReadXml](#dsrdtr)

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a>Deserializzare un DataSet o DataTable tramite JsonConvert

La popolare libreria Newtonsoft di terze parti [JSON.NET](https://www.newtonsoft.com/json) può essere usata per deserializzare le `DataSet` istanze di e `DataTable` , come illustrato nel codice seguente:

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

La deserializzazione di un oggetto `DataSet` o `DataTable` in questo modo da un BLOB JSON non attendibile non è sicura. Questo modello è vulnerabile a un attacco di tipo Denial of Service. Un attacco di questo tipo potrebbe causare l'arresto anomalo dell'app o il rendering non risponde.

> [!NOTE]
> Microsoft non garantisce né supporta l'implementazione di librerie di terze parti come _Newtonsoft.Json_. Queste informazioni vengono fornite per completezza ed è accurate al momento della stesura di questo articolo.

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a>Deserializzare un DataSet o un DataTable tramite BinaryFormatter

Gli sviluppatori non devono mai usare i `BinaryFormatter` `NetDataContractSerializer` `SoapFormatter` formattatori non ***sicuri*** correlati,, o per deserializzare un' `DataSet` istanza di o `DataTable` da un payload non attendibile:

* Questa operazione è soggetta a un attacco di esecuzione del codice remoto completo.
* L'uso di un oggetto personalizzato `SerializationBinder` non è sufficiente per evitare tale attacco.

## <a name="safe-replacements"></a>Sostituzioni sicure

Per le app che possono:

* Accettare `DataSet` o `DataTable` tramite un endpoint SOAP. asmx o un endpoint WCF.
* Deserializzare i dati non attendibili in un'istanza di `DataSet` o `DataTable` .

Prendere in considerazione la sostituzione del modello a oggetti per usare [Entity Framework](/ef). Entity Framework:

* È un Framework avanzato, moderno e orientato a oggetti, che può rappresentare dati relazionali.
* Offre [un ecosistema diversificato](/ef/core/providers/) di provider di database per semplificare la progettazione di query di database tramite i modelli a oggetti Entity Framework.
* Offre protezioni predefinite per la deserializzazione dei dati da origini non attendibili.

Per le app che usano `.aspx` gli endpoint SOAP, provare a modificare tali endpoint per l'uso di [WCF](/dotnet/framework/wcf/). WCF è una sostituzione più completa per i `.asmx` servizi Web. Gli endpoint WCF [possono essere esposti tramite SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) per la compatibilità con i chiamanti esistenti.
