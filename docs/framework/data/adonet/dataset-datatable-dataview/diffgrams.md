---
title: DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2bf736445a041ec678ab30474da51fddfba1773b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934486"
---
# <a name="diffgrams"></a>DiffGram
DiffGram è un formato XML che consente di identificare le versioni correnti e originali degli elementi di dati. Il formato DiffGram viene usato dal tipo <xref:System.Data.DataSet> per caricare e conservare il contenuto e per serializzare tale contenuto in modo da consentirne il trasporto tramite una connessione di rete. Quando un <xref:System.Data.DataSet> oggetto viene scritto come DiffGram, popola il DiffGram con tutte le informazioni necessarie per ricreare accuratamente il contenuto, ma non lo schema, <xref:System.Data.DataSet>di, inclusi i valori di colonna sia dall'oggetto **originale** che **da** Versioni di riga correnti, informazioni sugli errori delle righe e ordine delle righe.  
  
 Quando si invia e si recupera un tipo <xref:System.Data.DataSet> da un servizio Web XML, il formato DiffGram viene usato implicitamente. Inoltre, quando si carica il contenuto di <xref:System.Data.DataSet> un oggetto da XML utilizzando il metodo **ReadXml** o quando si scrive il contenuto <xref:System.Data.DataSet> di un oggetto in XML utilizzando il metodo **WriteXml** , è possibile specificare che il contenuto venga letto o scritto come DiffGram. Per ulteriori informazioni, vedere [caricamento di un DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) e [scrittura del contenuto del set di dati come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Benché il formato DiffGram venga usato principalmente da .NET Framework come formato di serializzazione per il contenuto di un tipo <xref:System.Data.DataSet>, è possibile usare i DiffGram per modificare i dati delle tabelle di un database Microsoft SQL Server.  
  
 Un DiffGram viene generato scrivendo il contenuto di tutte le tabelle in un  **\<elemento DiffGram >** .  
  
### <a name="to-generate-a-diffgram"></a>Per generare un Diffgram  
  
1. Generare un elenco di tabelle radice, ovvero senza elementi padre.  
  
2. Per ogni tabella e per i relativi discendenti nell'elenco, scrivere la versione corrente di tutte le righe nella prima sezione del Diffgram.  
  
3. Per ogni tabella in <xref:System.Data.DataSet>, scrivere la versione originale di tutte le righe, se presenti,  **\<** nella sezione before > del DiffGram.  
  
4. Per le righe che contengono errori, scrivere il contenuto dell'errore  **\<** nella sezione Errors > del DiffGram.  
  
 Un Diffgram viene elaborato nell'ordine a partire dal file XML fino alla fine.  
  
### <a name="to-process-a-diffgram"></a>Per elaborare un Diffgram  
  
1. Elaborare la prima sezione del Diffgram che contiene la versione corrente delle righe.  
  
2. Elaborare il secondo o la  **\<sezione before >** che contiene la versione di riga originale delle righe modificate ed eliminate.  
  
    > [!NOTE]
    > Se una riga è contrassegnata come eliminata, con l'operazione di eliminazione è possibile che vengano rimossi anche i relativi discendenti, a seconda della proprietà `Cascade` dell'oggetto <xref:System.Data.DataSet> corrente.  
  
3. Elaborare la sezione degli  **\<errori >** . Impostare le informazioni sull'errore per la riga e la colonna specificate per ogni elemento di questa sezione.  
  
> [!NOTE]
> Se si imposta <xref:System.Data.XmlWriteMode> su Diffgram, il contenuto dell'oggetto <xref:System.Data.DataSet> di destinazione può essere diverso da quello dell'oggetto <xref:System.Data.DataSet> originale.  
  
## <a name="diffgram-format"></a>Formato DiffGram  
 Il formato DiffGram è suddiviso in tre sezioni: i dati correnti, i dati originali (o "precedenti") e una sezione relativa agli errori, come illustrato nell'esempio seguente.  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 Il formato DiffGram è costituito dai seguenti blocchi di dati:  
  
 **\<**  ***DataInstance***  **>**  
 Il nome di questo elemento, ***DataInstance***, viene usato a scopo di spiegazione in questa documentazione. Un elemento DataInstance rappresenta un <xref:System.Data.DataSet> oggetto o una riga di <xref:System.Data.DataTable>un oggetto. Anziché DataInstance, l'elemento conterrà il nome dell'oggetto <xref:System.Data.DataSet> o. <xref:System.Data.DataTable> In questo blocco del formato DiffGram sono contenuti i dati correnti, indipendentemente dalle eventuali modifiche a tali dati. Un elemento, o riga, modificato viene identificato con l'annotazione **diffgr: hasChanges** .  
  
 **\<diffgr:before>**  
 In questo blocco del formato DiffGram è contenuta la versione originale di una riga. Gli elementi in questo blocco vengono associati agli elementi nel blocco ***DataInstance*** usando l'annotazione **diffgr: ID** .  
  
 **\<diffgr:errors>**  
 Questo blocco del formato DiffGram contiene informazioni sull'errore per una riga specifica nel blocco ***DataInstance*** . Gli elementi in questo blocco vengono associati agli elementi nel blocco ***DataInstance*** usando l'annotazione **diffgr: ID** .  
  
## <a name="diffgram-annotations"></a>Annotazioni DiffGram  
 I DiffGram usano diverse annotazioni per correlare elementi presenti nei vari blocchi di DiffGram, che rappresentano diverse versioni di riga o informazioni relative agli errori nel tipo <xref:System.Data.DataSet>.  
  
 Nella tabella seguente vengono descritte le annotazioni DiffGram definite nello spazio dei nomi DiffGram **urn: schemas-microsoft-com: XML-DiffGram-V1**.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**id**|Utilizzato per associare gli **>** elementi **\<**  **\<del diffgr: before >** e  **\<diffgr: Errors >** blocchi agli elementi nel blocco DataInstance. I valori con l'annotazione **diffgr: ID** sono nel formato *[TableName] [IdentificatoreRiga]* . Ad esempio: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Identifica l'elemento **\<** del blocco DataInstance **>** che è l'elemento padre dell'elemento corrente. I valori con l'annotazione **diffgr: parentID** sono nel formato *[TableName] [IdentificatoreRiga]* . Ad esempio: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifica una riga nel **\<** blocco DataInstance **>** come modificata. L'annotazione **HasChanges** può avere uno dei due valori seguenti:<br /><br /> **inserted**<br /> Identifica una riga **aggiunta** .<br /><br /> **modified**<br /> Identifica una riga **modificata** che contiene una  **\<** versione di riga originale nel blocco diffgr: before >. Si noti che nelle righe eliminate sarà presente una **>** **\<**  **\<** versione di riga originale in diffgr: before > Block, ma non sarà presente alcun elemento annotato nel blocco DataInstance.|  
|**hasErrors**|Identifica una **\<** riga nel blocco DataInstance **>** con un **RowError**. L'elemento Error viene inserito nel  **\<blocco diffgr: Errors >** .|  
|**Erroree**|Contiene il testo di **RowError** per un particolare elemento nel  **\<blocco diffgr: Errors >** .|  
  
 Quando legge o scrive il proprio contenuto come DiffGram, il tipo <xref:System.Data.DataSet> include ulteriori annotazioni. Nella tabella seguente vengono descritte le annotazioni aggiuntive definite nello spazio dei nomi **urn: schemas-microsoft-com: xml-msdata**.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**RowOrder**|Conserva l'ordine di riga dei dati originali e identifica l'indice di una riga in un particolare tipo <xref:System.Data.DataTable>.|  
|**Nascosto**|Identifica una colonna con la proprietà **ColumnMapping** impostata su **MappingType. Hidden**. L'attributo viene scritto nel formato **msdata: Hidden** *[ColumnName]* = "*value*". Ad esempio: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Notare che le colonne nascoste vengono scritte come attributo DiffGram solo se in tali colonne sono presenti dati. In caso contrario, vengono ignorate.|  
  
## <a name="sample-diffgram"></a>Esempio di DiffGram  
 Di seguito viene riportato un esempio di formato DiffGram. Questo esempio mostra il risultato di un aggiornamento a una riga prima della conferma delle modifiche. La riga con CustomerID pari a "ALFKI" è stata modificata, ma non aggiornata. Di conseguenza, esiste una riga **corrente** con **diffgr: ID** " **\<** Customers1" nel blocco DataInstance **>** e una riga **originale** con **diffgr: ID** "Customers1" nel  **\< diffgr: prima** del blocco >. La riga con CustomerID "Anat" include **RowError**, quindi viene annotata con `diffgr:hasErrors="true"` ed è presente un elemento  **\<** correlato nel blocco diffgr: Errors >.  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Scrittura del contenuto di DataSet come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
