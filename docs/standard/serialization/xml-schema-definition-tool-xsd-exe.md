---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: 6ec99e77db4215184547ea2bbbe0d1ff8ad3c286
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389769"
---
# <a name="xml-schema-definition-tool-xsdexe"></a>XML Schema Definition Tool (Xsd.exe)

Lo strumento XML Schema Definition (Xsd.exe) consente di generare classi Common Language Runtime o XML Schema da file XDR, XML e XSD o da classi di un assembly di runtime.

Lo strumento XML Schema Definition (Xsd.exe) in genere si trova nel percorso seguente:
_C:\\Programmi (x86)\\Microsoft\\SDK\\Di\\Windows\\.netversion bin NETFX\\_

## <a name="syntax"></a>Sintassi

Eseguire lo strumento dalla riga di comando.

```console
xsd file.xdr [-outputdir:directory][/parameters:file.xml]
xsd file.xml [-outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [-outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [-outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```
  
> [!TIP]
> Affinché gli strumenti di .NET Framework `Path` `Include`funzionino `Lib` correttamente, è necessario impostare correttamente le variabili di ambiente , e . attraverso l'esecuzione di SDKVars.bat, che si trova nella directory \<SDK>\v2.0\Bin. SDKVars.bat deve essere eseguito in ogni shell di comandi.

## <a name="argument"></a>Argomento

|Argomento|Descrizione|
|--------------|-----------------|
|*file.estensione*|Specifica il file di input da convertire. È necessario specificare l'estensione come uno dei seguenti: .xdr, .xml, .xsd, .dll o .exe.<br /><br /> Se si specifica un file di schema XDR (estensione xrd), lo schema XRD verrà convertito in uno schema XSD. Il file di output avrà lo stesso nome dello schema XDR, ma un'estensione xsd.<br /><br /> Se si specifica un file XML (estensione xml), verrà dedotto uno schema dai dati del file e prodotto uno schema XSD. Il file di output avrà lo stesso nome del file XML, ma un'estensione xsd.<br /><br /> Se si specifica un file di XML Schema (estensione xsd), verrà generato codice sorgente per gli oggetti di runtime corrispondenti allo schema XML.<br /><br /> Se si specifica un file di assembly di runtime (estensione EXE o DLL), verranno generati schemi per uno o più tipi di questo assembly. È possibile utilizzare l'opzione `/type` per specificare i tipi per i quali generare schemi. Gli schemi di output vengono denominati schema0.xsd, schema1.xsd e così via. In Xsd.exe vengono prodotti più schemi solo se i tipi forniti specificano uno spazio dei nomi con l'attributo personalizzato `XMLRoot`.|

## <a name="general-options"></a>Opzioni generali

|Opzione|Descrizione|
|------------|-----------------|
|**/h\[elp\]**|Visualizza la sintassi e le opzioni di comando dello strumento.|
|**/o\[utputdir\]:**_directory_|Specifica la directory per i file di output. Questo argomento può apparire una sola volta. Il valore predefinito è la directory corrente.|
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|
|**/p\[arametri\]:**_file.xml_|Legge le opzioni per diverse modalità operative dal file con estensione xml specificato. La forma abbreviata è `/p:`. Per ulteriori informazioni, vedere la sezione [Osservazioni.](#remarks)|

## <a name="xsd-file-options"></a>Opzioni per i file XSD
 È necessario specificare una sola delle opzioni elencate di seguito per i file XSD.

|Opzione|Descrizione|
|------------|-----------------|
|**/c\[lasses\]**|Genera classi che corrispondono allo schema specificato. Per leggere i dati XML nell'oggetto, usare il metodo <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType>.|
|**/d\[ataset\]**|Genera una classe derivata da <xref:System.Data.DataSet> che corrisponde allo schema specificato. Per leggere i dati XML nella classe derivata, usare il metodo <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType>.|

 È inoltre possibile specificare una o più opzioni tra quelle riportate di seguito per i file XSD.

|Opzione|Descrizione|
|------------|-----------------|
|**/e\[\]lement :**_elemento_|Specifica l'elemento dello schema per il quale generare codice. Per impostazione predefinita, sono specificati tutti gli elementi. È possibile specificare questo argomento più volte.|
|**/enableDataBinding**|Implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> su tutti i tipi generati per consentire l'associazione dati. La forma abbreviata è `/edb`.|
|**/enableLinqDataSet**|(Forma breve: `/eld`.) Specifica che è possibile eseguire una query sul DataSet generato utilizzando LINQ to DataSet. Questa opzione viene utilizzata quando è specificata anche l'opzione per i /dataset . Per altre informazioni, vedere [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) (Panoramica di LINQ to DataSet) e [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md) (Esecuzione di query su dataset tipizzati). Per informazioni generali sull'utilizzo di LINQ, vedere [Language-Integrated Query (LINQ) - C'](../../csharp/programming-guide/concepts/linq/index.md) o [Language-Integrated Query (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).|
|**/f\[ieeele\]**|Genera campi anziché proprietà. Per impostazione predefinita, vengono generate le proprietà.|
|**/l\[\]anguage :**_lingua_|Specifica il linguaggio di programmazione da utilizzare. È possibile scegliere tra `CS` (C#, il linguaggio predefinito), `VB` (Visual Basic), `JS` (JScript) o `VJS` (Visual J#). È anche possibile specificare un nome completo per una classe che implementa <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>|
|**/n\[amespace\]:** spazio dei_nomi_|Specifica lo spazio dei nomi del runtime per i tipi generati. Lo spazio dei nomi predefinito è `Schemas`.|
|**/nologo**|Evita la visualizzazione del messaggio di avvio.|
|**/ORDER**|Genera identificatori di ordine espliciti su tutti i membri particella.|
|**/o\[\]ut :**_nomedirectory_|Specifica la directory di output in cui inserire i file. Il valore predefinito è la directory corrente.|
|**/u\[\]ri :**_uri_|Specifica l'URI degli elementi dello schema per il quale generare codice. Questo URI, se presente, viene applicato a tutti gli elementi specificati con l'opzione `/element`.|

## <a name="dll-and-exe-file-options"></a>Opzioni per i file DLL ed EXE

|Opzione|Descrizione|
|------------|-----------------|
|**/t\[ype\]:**_nometipo_|Specifica il nome del tipo per il quale creare uno schema. È possibile specificare più argomenti type. Se *nometipo* non specifica uno spazio dei nomi, Xsd.exe associa tutti i tipi nell'assembly con il tipo specificato. Se *nometipo* specifica uno spazio dei nomi, viene associato solo il tipo specifico. Se *nometipo* termina con un asterisco (\*), vengono associati tutti i tipi che iniziano con la stringa che precede \*. Se si omette l'opzione `/type`, verranno generati schemi per tutti i tipi dell'assembly.|

## <a name="remarks"></a>Osservazioni

Nella tabella riportata di seguito vengono illustrate le operazioni eseguite da Xsd.exe.

| | |
|------------|-----------------|
|Da XDR a XSD|Generare uno schema XML da un file di schema con dati XML ridotti. XDR è un precedente formato di schema basato su XML.|
|Da XML a XSD|Generare uno schema XML da un file XML.|
|Da XSD a dataset|Generare classi <xref:System.Data.DataSet> di Common Language Runtime da un file di schema XSD. Le classi generate forniscono un modello a oggetti elaborato per i dati XML regolari.|
|Da XSD a classi|Generare classi di runtime da un file di schema XSD. Le classi generate possono essere utilizzate con <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> per leggere e scrivere il codice XML basato sullo schema.|
|Da classi a XSD| Generare uno schema XML da uno o più tipi presenti in un file di assembly di runtime. Lo schema generato definisce il <xref:System.Xml.Serialization.XmlSerializer>formato XML utilizzato dall'oggetto .|

 Xsd.exe consente solo di modificare gli schemi XML che seguono il linguaggio XSD (XML Schema Definition) proposto da W3C (World Wide Web Consortium). Per ulteriori informazioni sulla proposta XML Schema Definition <https://w3.org>o sullo standard XML, vedere .

## <a name="setting-options-with-an-xml-file"></a>Impostazione delle opzioni con un file XML

Usando l'opzione `/parameters`, è possibile specificare un singolo file XML che imposta diverse opzioni. Le opzioni che è possibile impostare dipendono dalla modalità di utilizzo dello strumento XSD.exe. È possibile scegliere di generare schemi, file di codice o file di codice con funzionalità `DataSet`. Ad esempio, è possibile impostare l'elemento `<assembly>` sul nome di un file eseguibile (.exe) o di una libreria di tipi (.dll) durante la generazione di uno schema, ma non durante la generazione di un file di codice. Nel codice XML riportato di seguito viene illustrato come utilizzare l'elemento `<generateSchemas>` con un determinato file eseguibile:

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

Se il codice XML precedente è contenuto in un file `/parameters` denominato GenerateSchemas.xml, utilizzare l'opzione digitando quanto segue al prompt dei comandi e premendo **INVIO:**

```console
 xsd /p:GenerateSchemas.xml
```

Se invece si genera uno schema per un singolo tipo trovato nell'assembly, è possibile utilizzare il codice XML riportato di seguito:

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

Per utilizzare il codice riportato sopra è necessario specificare anche il nome dell'assembly al prompt dei comandi. Immettere quanto segue al prompt dei comandi (presupponendo che il file XML sia denominato GenerateSchemaFromType.xml):

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

Per l'elemento `<generateSchemas>` è necessario specificare solo una delle seguenti opzioni.

|Elemento|Descrizione|
|-------------|-----------------|
|\<assembly>|Specifica un assembly dal quale generare lo schema.|
|\<type>|Specifica un tipo trovato in un assembly per il quale generare uno schema.|
|\<xml>|Specifica un file XML per il quale generare uno schema.|
|\<xdr>|Specifica un file XDR per il quale generare uno schema.|

Per generare un file di codice, utilizzare l'elemento `<generateClasses>`. Nell'esempio riportato di seguito viene generato un file di codice. Sono presenti anche due attributi che consentono di impostare il linguaggio di programmazione e lo spazio dei nomi del file generato.

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 Per l'elemento `<generateClasses>` è possibile impostare le seguenti opzioni.

|Elemento|Descrizione|
|-------------|-----------------|
|\<element>|Specifica un elemento nel file XSD per il quale generare codice.|
|\<schemaImporterExtensions>|Specifica un tipo derivato dalla classe <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>.|
|\<schema>|Specifica un file di XML Schema per il quale generare un codice. È possibile specificare più file XML Schema usando più elementi \<schema>.|

Nella tabella riportata di seguito sono descritti gli attributi che è possibile utilizzare con l'elemento `<generateClasses>`.

|Attributo|Descrizione|
|---------------|-----------------|
|Linguaggio|Specifica il linguaggio di programmazione da utilizzare. È possibile scegliere tra `CS` (C#, il linguaggio predefinito), `VB` (Visual Basic), `JS` (JScript) o `VJS` (Visual J#). È anche possibile specificare un nome completo per una classe che implementa <xref:System.CodeDom.Compiler.CodeDomProvider>.|
|namespace|Specifica lo spazio dei nomi per il codice generato. Lo spazio dei nomi deve essere conforme agli standard CLR, ad esempio non devono essere presenti spazi o barre rovesciate.|
|opzioni|Uno dei valori seguenti: `none`, `properties` (genera proprietà invece di campi pubblici), `order` o `enableDataBinding` (vedere le opzioni `/order` e `/enableDataBinding` nella sezione precedente "Opzioni per i file XSD").|

 È anche possibile controllare la modalità di generazione del codice `DataSet` utilizzando l'elemento `<generateDataSet>`. Il codice XML seguente specifica `DataSet` che il codice <xref:System.Data.DataTable> generato utilizza strutture (ad esempio la classe) per creare codice Visual Basic per un elemento specificato. Le strutture di DataSet generate supporteranno le query LINQ.

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

Per l'elemento `<generateDataSet>` è possibile impostare le seguenti opzioni.

|Elemento|Descrizione|
|-------------|-----------------|
|\<schema>|Specifica un file di XML Schema per il quale generare un codice. È possibile specificare più file XML Schema usando più elementi \<schema>.|

 Nella tabella riportata di seguito sono descritti gli attributi che è possibile utilizzare con l'elemento `<generateDataSet>`.

|Attributo|Descrizione|
|---------------|-----------------|
|enableLinqDataSet|Specifica che il dataset generato può essere sottoposto a query mediante LINQ to DataSet. Il valore predefinito è false.|
|Linguaggio|Specifica il linguaggio di programmazione da utilizzare. È possibile scegliere tra `CS` (C#, il linguaggio predefinito), `VB` (Visual Basic), `JS` (JScript) o `VJS` (Visual J#). È anche possibile specificare un nome completo per una classe che implementa <xref:System.CodeDom.Compiler.CodeDomProvider>.|
|namespace|Specifica lo spazio dei nomi per il codice generato. Lo spazio dei nomi deve essere conforme agli standard CLR, ad esempio non devono essere presenti spazi o barre rovesciate.|

 Alcuni attributi possono essere impostati sull'elemento `<xsd>` di livello più alto. È possibile utilizzare queste opzioni con uno qualsiasi degli elementi figlio (`<generateSchemas>`,`<generateClasses>` o `<generateDataSet>`). Nell'esempio di codice XML riportato di seguito viene generato codice per un elemento denominato IDItems nella directory di output MyOutputDirectory.

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

Nella tabella riportata di seguito sono descritti gli attributi che è possibile utilizzare con l'elemento `<xsd>`.

|Attributo|Descrizione|
|---------------|-----------------|
|output|Nome della directory in cui verrà inserito lo schema o il file di codice generato.|
|nologo|Evita la visualizzazione del messaggio di avvio. Impostare su `true` o `false`.|
|help|Visualizza la sintassi e le opzioni di comando dello strumento. Impostare su `true` o `false`.|

## <a name="examples"></a>Esempi
 Il comando che segue genera uno schema XML da `myFile.xdr` e lo salva nella directory corrente.

```console
xsd myFile.xdr
```

Il comando che segue genera uno schema XML da `myFile.xml` e lo salva nella directory specificata.

```console
xsd myFile.xml /outputdir:myOutputDir
```

Il comando che segue genera un set di dati che corrisponde allo schema specificato nel linguaggio C# e lo salva con il nome `XSDSchemaFile.cs` nella directory corrente.

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

Il comando che segue genera schemi XML per tutti i tipi dell'assembly `myAssembly.dll` e li salva con il nome `schema0.xsd` nella directory corrente.

```console
xsd myAssembly.dll
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [Strumenti](../../../docs/framework/tools/index.md)
- [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [Cenni preliminari su LINQ to DataSet](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [Esecuzione di query su dataset tipizzati](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [LINQ (Query integrata nel linguaggio) (C](../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ (Language-Integrated Query) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/index.md)
