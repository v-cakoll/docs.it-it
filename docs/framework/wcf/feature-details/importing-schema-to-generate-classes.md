---
title: Importazione dello schema per generare classi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractImporter class
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
ms.openlocfilehash: 01f5162727a213fa5dcdf8a70e4e8e4c3627f086
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596903"
---
# <a name="importing-schema-to-generate-classes"></a>Importazione dello schema per generare classi
Per generare classi da schemi utilizzabili con Windows Communication Foundation (WCF), utilizzare la <xref:System.Runtime.Serialization.XsdDataContractImporter> classe. In questo argomento viene descritto il processo e le relative varianti.  
  
## <a name="the-import-process"></a>Processo di importazione
 Il processo di importazione dello schema ha inizio con una classe <xref:System.Xml.Schema.XmlSchemaSet> e produce una classe <xref:System.CodeDom.CodeCompileUnit>.  
  
 Il `XmlSchemaSet` fa parte del modello SOM (Schema Object Model) del .NET Framework che rappresenta un set di documenti dello schema XSD (XML Schema Definition Language). Per creare un oggetto `XmlSchemaSet` da un set di documenti XSD, deserializzare ogni documento in un oggetto <xref:System.Xml.Schema.XmlSchema> (mediante <xref:System.Xml.Serialization.XmlSerializer>) e aggiungere questi oggetti a una nuova classe `XmlSchemaSet`.  
  
 `CodeCompileUnit`Fa parte della Code Document Object Model (CodeDom) del .NET Framework che rappresenta .NET Framework codice in modo astratto. Per generare il codice effettivo da una classe `CodeCompileUnit`, usare una sottoclasse della classe <xref:System.CodeDom.Compiler.CodeDomProvider>, ad esempio la classe <xref:Microsoft.CSharp.CSharpCodeProvider> o <xref:Microsoft.VisualBasic.VBCodeProvider>.  
  
### <a name="to-import-a-schema"></a>Per importare uno schema  
  
1. Creare un'istanza di <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2. Facoltativa. Passare `CodeCompileUnit` nel costruttore. I tipi generati durante l'importazione dello schema vengono aggiunti a questa istanza di `CodeCompileUnit` anziché iniziare con un'istanza `CodeCompileUnit` vuota.  
  
3. Facoltativa. Chiamare uno dei metodi <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A> . Il metodo determina se lo schema specificato è un schema del contratto dati valido e può essere importato. Il metodo `CanImport` presenta gli stessi overload di `Import` (il passaggio successivo).  
  
4. Chiamare uno dei metodi `Import` di overload, ad esempio il metodo <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29>.  
  
     L'overload più semplice accetta una classe `XmlSchemaSet` e importa tutti i tipi, incluso quelli anonimi, presenti in tale set di schemi. Gli altri overload consentono di specificare il tipo XSD o un elenco di tipi da importare (in una classe <xref:System.Xml.XmlQualifiedName> o una raccolta di oggetti `XmlQualifiedName`). In questo caso, vengono importati solo i tipi specificati. Un overload accetta una classe <xref:System.Xml.Schema.XmlSchemaElement> che importa un elemento specifico fuori dalla classe `XmlSchemaSet`, insieme al tipo associato (indipendentemente dal fatto che sia anonimo o meno). Questo overload restituisce una classe `XmlQualifiedName` che rappresenta il nome del contratto dati del tipo generato per questo elemento.  
  
     Più chiamate al metodo `Import` determinano l'aggiunta di più elementi alla stessa classe `CodeCompileUnit`. Se esiste già un tipo in `CodeCompileUnit` , non ne viene generato un altro. È consigliabile chiamare più volte `Import` sullo stesso `XsdDataContractImporter` anziché usare più oggetti `XsdDataContractImporter`. Questa procedura è consigliata per evitare la generazione di tipi duplicati.  
  
    > [!NOTE]
    > Se si verifica un errore durante l'importazione, lo stato della classe `CodeCompileUnit` sarà imprevedibile. Se si usa una classe `CodeCompileUnit` da un'importazione non riuscita, è possibile esporre il sistema a vulnerabilità della protezione.  
  
5. Accedere a `CodeCompileUnit` mediante la proprietà <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> .  
  
### <a name="import-options-customizing-the-generated-types"></a>Opzioni di importazione: personalizzazione dei tipi generati  
 È possibile impostare la proprietà <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> di <xref:System.Runtime.Serialization.XsdDataContractImporter> su un'istanza della classe <xref:System.Runtime.Serialization.ImportOptions> per controllare vari aspetti del processo di importazione. Alcune opzioni influenzano direttamente i tipi generati.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Controllo del livello di accesso (opzione GenerateInternal o /internal)  
 Corrisponde all'opzione **/Internal** dello [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 In genere, i tipi pubblici vengono generati dallo schema, con campi privati e proprietà dei membri dati pubblici corrispondenti. Per generare invece tipi interni, impostare la proprietà <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> su `true`.  
  
 Nell'esempio seguente viene illustrato uno schema trasformato in una classe interna quando la proprietà <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> è impostata su `true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Controllo degli spazi dei nomi (opzione Namespaces o /namespace)  
 Corrisponde all'opzione **/namespace** dello `Svcutil.exe` strumento.  
  
 In genere, i tipi generati dallo schema vengono generati in .NET Framework spazi dei nomi, con ogni spazio dei nomi XSD corrispondente a un particolare .NET Framework spazio dei nomi in base a un mapping descritto in [riferimento allo schema del contratto dati](data-contract-schema-reference.md). È possibile personalizzare questo mapping impostando la proprietà <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> su <xref:System.Collections.Generic.Dictionary%602>. Se un determinato spazio dei nomi XSD viene trovato nel dizionario, anche lo spazio dei nomi .NET Framework corrispondente viene tratto dal dizionario.  
  
 Si consideri ad esempio lo schema seguente.  
  
 [!code-xml[c_SchemaImportExport#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  
  
 Nell'esempio seguente viene utilizzata la `Namespaces` proprietà per eseguire il mapping dello `http://schemas.contoso.com/carSchema` spazio dei nomi a "contoso. Cars".  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Aggiunta di SerializableAttribute (opzione GenerateSerializable o /serializable)  
 Corrisponde all'opzione **/Serializable** dello `Svcutil.exe` strumento.  
  
 A volte è importante che i tipi generati dallo schema siano utilizzabili con i motori di serializzazione di Runtime .NET Framework (ad esempio, le <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classi e). Questa operazione è utile quando si usano i tipi per .NET Framework comunicazione remota. Per abilitare questo aspetto è necessario applicare l'attributo <xref:System.SerializableAttribute> ai tipi generati in aggiunta all'attributo <xref:System.Runtime.Serialization.DataContractAttribute> normale. L'attributo viene generato automaticamente se l'opzione di importazione `GenerateSerializable` è impostata su `true`.  
  
 Nell'esempio seguente viene illustrata la classe `Vehicle` generata con l'opzione di importazione `GenerateSerializable` impostata su `true`.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Aggiunta del supporto dei data binding (opzione EnableDataBinding o /enableDataBinding)  
 Corrisponde all'opzione **/EnableDataBinding** dello strumento Svcutil. exe.  
  
 In alcuni casi può essere necessario associare i tipi generati dallo schema ai componenti dell'interfaccia utente grafica in modo che qualsiasi aggiornamento alle istanze di questi tipi aggiorni automaticamente l'interfaccia utente. La classe `XsdDataContractImporter` può generare tipi che implementano l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> in modo che qualsiasi modifica delle proprietà generi un evento. Se si generano tipi da usare con un ambiente di programmazione dell'interfaccia utente client che supporta questa interfaccia (ad esempio Windows Presentation Foundation (WPF)), impostare la <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> proprietà su `true` per abilitare questa funzionalità.  
  
 Nell'esempio seguente viene illustrata la classe `Vehicle` generata con la proprietà <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> impostata su `true`.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Opzioni di importazione: scelta dei tipi di raccolta  
 Due modelli speciali in XML rappresentano raccolte di elementi: elenchi di elementi e associazioni tra due elementi. Di seguito è riportato un esempio di un elenco di stringhe.  
  
 [!code-xml[C_SchemaImportExport#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  
  
 Nell'esempio seguente viene mostrata un'associazione tra una stringa e un numero intero (`city name` e `population`).  
  
 [!code-xml[C_SchemaImportExport#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  
  
> [!NOTE]
> Qualsiasi associazione può essere considerata un elenco. Ad esempio, è possibile visualizzare l'associazione precedente come un elenco di oggetti `city` complessi che presentano due campi (un campo stringa e un campo numero intero). Entrambi i modelli sono rappresentati nello schema XSD. Non esiste alcun modo per distinguere tra un elenco e un'associazione, quindi tali modelli vengono sempre considerati come elenchi, a meno che nello schema non sia presente un'annotazione speciale specifica di WCF. L'annotazione indica che un modello specifico rappresenta un'associazione. Per ulteriori informazioni, vedere [riferimento allo schema del contratto dati](data-contract-schema-reference.md).  
  
 In genere, un elenco viene importato come contratto dati della raccolta che deriva da un elenco generico o come matrice di .NET Framework, a seconda che lo schema segua o meno il modello di denominazione standard per le raccolte. Questa operazione viene descritta più dettagliatamente nei [tipi di raccolta nei contratti dati](collection-types-in-data-contracts.md). Le associazioni normalmente vengono importate come un tipo <xref:System.Collections.Generic.Dictionary%602> o un contratto dati della raccolta che deriva dall'oggetto dizionario. Si consideri ad esempio lo schema seguente.  
  
 [!code-xml[c_SchemaImportExport#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  
  
 Questo schema viene importato come segue (vengono visualizzati i campi anziché le proprietà per migliorare la leggibilità).  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 È possibile personalizzare i tipi di raccolta generati per tali modelli di schema. Ad esempio, è possibile generare raccolte che derivano da <xref:System.ComponentModel.BindingList%601> anziché dalla classe <xref:System.Collections.Generic.List%601> per associare il tipo a una casella di riepilogo e fare in modo che venga aggiornato automaticamente quando il contenuto della raccolta viene modificato. A questo scopo, impostare la proprietà <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> della classe <xref:System.Runtime.Serialization.ImportOptions> su un elenco di tipi di raccolta da usare (successivamente indicati come i tipi a cui si fa riferimento). Quando si importa una raccolta, questo elenco di tipi di raccolta a cui si fa riferimento viene analizzato e la raccolta più corrispondente viene usata, se ne viene trovata una. Le associazioni vengono messe in corrispondenza solo con i tipi che implementano l'interfaccia <xref:System.Collections.IDictionary> generica o non generica, mentre gli elenchi vengono messi in corrispondenza con qualsiasi tipo di raccolta supportato.  
  
 Ad esempio, se la proprietà <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> è impostata su una classe <xref:System.ComponentModel.BindingList%601>, the `people` nell'esempio precedente viene generato come segue.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Un tipo generico chiuso è considerato la corrispondenza migliore, ad esempio, se i tipi `BindingList(Of Integer)` e <xref:System.Collections.ArrayList> vengono passati alla raccolta di tipi a cui si fa riferimento, qualsiasi elenco di numeri interi trovato nello schema viene importato come un tipo `BindingList(Of Integer)`. Qualsiasi altro elenco, ad esempio, un `List(Of String)`, viene importato come un `ArrayList`.  
  
 Se viene aggiunto un tipo che implementa l'interfaccia `IDictionary` generica alla raccolta di tipi a cui si fa riferimento, i relativi parametri del tipo devono essere completamente aperti o completamente chiusi.  
  
 Non è consentito l'uso di duplicati. Ad esempio, non è possibile aggiungere `List(Of Integer)` e `Collection(Of Integer)` ai tipi a cui si fa riferimento. Questa operazione renderebbe impossibile determinare quale elemento deve essere usato quando nello schema è presente un elenco di numeri interi. I duplicati verranno rilevati solo se nello schema esiste un tipo che espone il problema dei duplicati. Se ad esempio lo schema importato non contiene elenchi di numeri interi, è consentito avere sia `List(Of Integer)` che `Collection(Of Integer)` nella raccolta di tipi a cui si fa riferimento, ma nessuno dei due elementi eserciterà alcun effetto.  
  
 Il meccanismo dei tipi della raccolta a cui si fa riferimento funziona ugualmente per le raccolte di tipi complessi (incluse le raccolte di altre raccolte) e non solo per raccolte di primitivi.  
  
 La `ReferencedCollectionTypes` proprietà corrisponde all'opzione **opzione/collectionType** dello strumento Svcutil. exe. Si noti che per fare riferimento a più tipi di raccolta, l'opzione **opzione/collectionType** deve essere specificata più volte. Se il tipo non è presente in MsCorLib. dll, è necessario fare riferimento anche all'assembly usando l'opzione **/Reference** .  
  
#### <a name="import-options-referencing-existing-types"></a>Opzioni di importazione: riferimento ai tipi esistenti  
 Occasionalmente, i tipi nello schema corrispondono ai tipi di .NET Framework esistenti e non è necessario generare questi tipi da zero. (questa sezione si applica solo ai tipi non di raccolta. Per i tipi di raccolta, vedere la sezione precedente).  
  
 Ad esempio, è possibile che si disponga di un contratto dati "Person" standard per tutta l'azienda che si desidera usare sempre quando si rappresenta una persona. Ogni volta che un servizio usa questo tipo e lo schema è presente nei metadati del servizio, è possibile riutilizzare il tipo `Person` esistente durante l'importazione di questo schema anziché generare un nuovo tipo per ogni servizio.  
  
 A tale scopo, passare un elenco di tipi di .NET Framework che si desidera riutilizzare nella raccolta <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> restituita dalla proprietà sulla <xref:System.Runtime.Serialization.ImportOptions> classe. Se uno di questi tipi presenta un nome del contratto dati e un spazio dei nomi corrispondenti al nome e allo spazio dei nomi di un tipo di schema, viene eseguito un confronto strutturale. Se viene determinato che i tipi hanno sia nomi corrispondenti che strutture corrispondenti, il tipo di .NET Framework esistente viene riutilizzato anziché generarne uno nuovo. Se corrisponde solo il nome ma non la struttura, viene generata un'eccezione. Si noti che non è consentito il controllo delle versioni quando si fa riferimento ai tipi (ad esempio, aggiungendo nuovi membri dati facoltativi). Le strutture devono corrispondere perfettamente.  
  
 È possibile aggiungere più tipi con lo stesso nome del contratto dati e lo stesso spazio dei nomi alla raccolta di tipi a cui si fa riferimento, fintanto che non vengono importati tipi dello schema con tale nome e spazio dei nomi. In questo modo è possibile aggiungere facilmente tutti i tipi di un assembly alla raccolta senza temere che vengano creati duplicati dei tipi che non sono presenti nello schema.  
  
 La `ReferencedTypes` proprietà corrisponde all'opzione **/Reference** in determinate modalità di funzionamento dello strumento Svcutil. exe.  
  
> [!NOTE]
> Quando si usa Svcutil. exe o (in Visual Studio) gli strumenti di **Aggiungi riferimento al servizio** , viene fatto automaticamente riferimento a tutti i tipi in mscorlib. dll.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Opzioni di importazione: importazione di schemi diversi dal contratto dati come tipi IXmlSerializable  
 <xref:System.Runtime.Serialization.XsdDataContractImporter> supporta un sottoinsieme limitato dello schema. Se sono presenti costrutti dello schema non supportati (ad esempio, attributi XML), il tentativo di importazione non riesce e viene generata un'eccezione. Tuttavia, l'impostazione della proprietà <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> su `true` estende l'intervallo di schemi supportati. Se impostato su `true`, <xref:System.Runtime.Serialization.XsdDataContractImporter> genera tipi che implementano l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable>. In questo modo viene consentito l'accesso diretto alla rappresentazione XML di questi tipi.  
  
##### <a name="design-considerations"></a>Considerazioni sulla progettazione  
  
- Può risultare difficile lavorare direttamente con la rappresentazione XML con tipizzazione debole, pertanto è consigliabile usare un motore di serializzazione alternativo, ad esempio <xref:System.Xml.Serialization.XmlSerializer>, per lavorare con schemi non compatibili con i contratti dati in modo fortemente tipizzato. Per ulteriori informazioni, vedere [utilizzo della classe XmlSerializer](using-the-xmlserializer-class.md).  
  
- Alcuni costrutti dello schema non possono essere importati da <xref:System.Runtime.Serialization.XsdDataContractImporter> anche se la proprietà <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> è impostata su `true`. Anche in questo caso, è consigliabile usare <xref:System.Xml.Serialization.XmlSerializer>.  
  
- I costrutti dello schema supportati sia quando è che <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> `true` `false` in sono descritti in [riferimento allo schema del contratto dati](data-contract-schema-reference.md).  
  
- Gli schemi per i tipi <xref:System.Xml.Serialization.IXmlSerializable> generati non conservano la fedeltà quando vengono importati ed esportati. In altre parole, se si esporta lo schema dai tipi generati e lo si importa come classi, non si ottiene lo schema originale.  
  
 È possibile combinare l'opzione <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> con l'opzione <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> descritta in precedenza. Per i tipi che devono essere generati come implementazioni <xref:System.Xml.Serialization.IXmlSerializable>, il controllo strutturale viene ignorato se si usa la funzionalità <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A>.  
  
 L' <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> opzione corrisponde all'opzione **/importXmlTypes** dello strumento Svcutil. exe.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Utilizzo dei tipi IXmlSerializable generati  
 I tipi `IXmlSerializable` generati contengono un campo privato denominato "nodesField" che restituisce una matrice di oggetti <xref:System.Xml.XmlNode>. Quando si deserializza un'istanza di questo tipo, è possibile accedere ai dati XML direttamente tramite questo campo usando il modello DOM XML. Quando si serializza un'istanza di questo tipo, è possibile impostare questo campo sui dati XML desiderati e verrà serializzato.  
  
 Questa operazione viene eseguita tramite l'implementazione dell'interfaccia `IXmlSerializable`. Nel tipo `IXmlSerializable` generato, l'implementazione <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> chiama il metodo <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> della classe <xref:System.Runtime.Serialization.XmlSerializableServices>. Si tratta di un metodo helper che converte il codice XML fornito tramite un <xref:System.Xml.XmlReader> in una matrice di oggetti <xref:System.Xml.XmlNode>. L'implementazione <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> esegue l'operazione inversa e converte la matrice di oggetti `XmlNode` a una sequenza di chiamate a <xref:System.Xml.XmlWriter>. Questa operazione viene eseguita mediante il metodo <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A>.  
  
 È possibile eseguire il processo di esportazione dello schema sulle classi `IXmlSerializable` generate. Come illustrato in precedenza, non è possibile ottenere lo schema originale. Si otterrà invece il tipo XSD standard "anyType", che è un carattere jolly per qualsiasi tipo XSD.  
  
 Questa operazione viene eseguita applicando l' <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> attributo alle classi generate `IXmlSerializable` e specificando un metodo che chiama il <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> metodo per generare il tipo "anyType".  
  
> [!NOTE]
> Il tipo <xref:System.Runtime.Serialization.XmlSerializableServices> esiste esclusivamente per supportare questa particolare funzionalità. Non è consigliabile usarlo per qualsiasi altro scopo.  
  
#### <a name="import-options-advanced-options"></a>Opzioni di importazione: opzioni avanzate  
 Di seguito sono elencate le opzioni importazione avanzate:  
  
- Proprietà <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A>. Specifica la classe <xref:System.CodeDom.Compiler.CodeDomProvider> da usare per generare il codice per le classi generate. Il meccanismo di importazione tenta di evitare funzionalità non supportate da <xref:System.CodeDom.Compiler.CodeDomProvider>. Se <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> non è impostato, viene utilizzato il set completo di .NET Framework funzionalità senza restrizioni.  
  
- Proprietà <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A>. È possibile specificare un'implementazione <xref:System.Runtime.Serialization.IDataContractSurrogate> con questa proprietà. <xref:System.Runtime.Serialization.IDataContractSurrogate> personalizza il processo di importazione. Per ulteriori informazioni, vedere [surrogati del contratto dati](../extending/data-contract-surrogates.md). Per impostazione predefinita, non viene usato alcun surrogato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- <xref:System.Runtime.Serialization.ImportOptions>
- [Informazioni di riferimento sullo schema del contratto di dati](data-contract-schema-reference.md)
- [Surrogati del contratto dati](../extending/data-contract-surrogates.md)
- [Importazione ed esportazione degli schemi](schema-import-and-export.md)
- [Esportazione di schemi da classi](exporting-schemas-from-classes.md)
- [Informazioni di riferimento sullo schema del contratto di dati](data-contract-schema-reference.md)
