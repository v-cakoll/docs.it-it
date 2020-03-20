---
title: DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2c521ef33c98234dac5f4b819a800cd524218462
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151156"
---
# <a name="diffgrams"></a>DiffGram
DiffGram è un formato XML che consente di identificare le versioni correnti e originali degli elementi di dati. Il formato DiffGram viene usato dal tipo <xref:System.Data.DataSet> per caricare e conservare il contenuto e per serializzare tale contenuto in modo da consentirne il trasporto tramite una connessione di rete. Quando <xref:System.Data.DataSet> un oggetto viene scritto come DiffGram, popola il DiffGram con tutte le informazioni necessarie <xref:System.Data.DataSet>per ricreare con precisione il contenuto, anche se non lo schema, di , inclusi i valori di colonna delle versioni di riga **Original** e **Current,** le informazioni sugli errori di riga e l'ordine delle righe.  
  
 Quando si invia e si recupera un tipo <xref:System.Data.DataSet> da un servizio Web XML, il formato DiffGram viene usato implicitamente. Inoltre, quando si carica <xref:System.Data.DataSet> il contenuto di un da XML utilizzando il <xref:System.Data.DataSet> **ReadXml** metodo, o quando si scrive il contenuto di un in XML utilizzando il **WriteXml** metodo, è possibile specificare che il contenuto deve essere letto o scritto come un DiffGram. Per ulteriori informazioni, vedere [Caricamento di un DataSet da XML](loading-a-dataset-from-xml.md) e Scrittura di contenuto [DataSet come dati XML](writing-dataset-contents-as-xml-data.md).  
  
 Benché il formato DiffGram venga usato principalmente da .NET Framework come formato di serializzazione per il contenuto di un tipo <xref:System.Data.DataSet>, è possibile usare i DiffGram per modificare i dati delle tabelle di un database Microsoft SQL Server.  
  
 Un Diffgram viene generato scrivendo il contenuto di tutte le tabelle in un ** \<elemento di diffgram>.**  
  
### <a name="to-generate-a-diffgram"></a>Per generare un Diffgram  
  
1. Generare un elenco di tabelle radice, ovvero senza elementi padre.  
  
2. Per ogni tabella e per i relativi discendenti nell'elenco, scrivere la versione corrente di tutte le righe nella prima sezione del Diffgram.  
  
3. Per ogni tabella <xref:System.Data.DataSet>di , scrivere la versione originale di tutte le righe, se presente, nella sezione ** \<prima>** del Diffgram.  
  
4. Per le righe con errori, scrivere ** \<** il contenuto dell'errore nella sezione relativa agli errori>del Diffgram.  
  
 Un Diffgram viene elaborato nell'ordine a partire dal file XML fino alla fine.  
  
### <a name="to-process-a-diffgram"></a>Per elaborare un Diffgram  
  
1. Elaborare la prima sezione del Diffgram che contiene la versione corrente delle righe.  
  
2. Elaborare la ** \<** seconda o la prima sezione>contenente la versione di riga originale delle righe modificate ed eliminate.  
  
    > [!NOTE]
    > Se una riga è contrassegnata come eliminata, con l'operazione di eliminazione è possibile che vengano rimossi anche i relativi discendenti, a seconda della proprietà `Cascade` dell'oggetto <xref:System.Data.DataSet> corrente.  
  
3. Elaborare ** \<** la sezione relativa>errori. Impostare le informazioni sull'errore per la riga e la colonna specificate per ogni elemento di questa sezione.  
  
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
  
 **\<**  ***IstanzaDati***  **>**  
 Il nome di questo elemento, ***DataInstance***, viene utilizzato a scopo esplicativo in questa documentazione. Un elemento ***DataInstance*** rappresenta una <xref:System.Data.DataSet> <xref:System.Data.DataTable>o una riga di un oggetto . Anziché *DataInstance*, l'elemento conterrà il nome dell'oggetto <xref:System.Data.DataSet> o <xref:System.Data.DataTable>. In questo blocco del formato DiffGram sono contenuti i dati correnti, indipendentemente dalle eventuali modifiche a tali dati. Un elemento, o riga, che è stato modificato viene identificato con l'annotazione **diffgr:hasChanges.**  
  
 **\<diffgr:prima>**  
 In questo blocco del formato DiffGram è contenuta la versione originale di una riga. Gli elementi in questo blocco vengono associati agli elementi nel blocco ***DataInstance*** utilizzando l'annotazione **diffgr:id.**  
  
 **\<diffgr:errori>**  
 Questo blocco del formato DiffGram contiene informazioni sull'errore per una determinata riga nel blocco ***DataInstance.*** Gli elementi in questo blocco vengono associati agli elementi nel blocco ***DataInstance*** utilizzando l'annotazione **diffgr:id.**  
  
## <a name="diffgram-annotations"></a>Annotazioni DiffGram  
 I DiffGram usano diverse annotazioni per correlare elementi presenti nei vari blocchi di DiffGram, che rappresentano diverse versioni di riga o informazioni relative agli errori nel tipo <xref:System.Data.DataSet>.  
  
 Nella tabella seguente vengono descritte le annotazioni DiffGram definite nello spazio dei nomi **urn:schemas-microsoft-com:xml-diffgram-v1**.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**id**|Utilizzato per associare gli elementi nel ** \<diffgr:before>** e **\<** **>** ** \<diffgr:errors>** blocchi agli elementi nel blocco ***DataInstance.*** I valori con l'annotazione **diffgr:id** sono nel formato *[NomeTabella][IdentificatoreRiga]*. Ad esempio `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Identifica quale elemento **\<** dal blocco ***DataInstance*** **>** è l'elemento padre dell'elemento corrente. I valori con l'annotazione **diffgr:parentId** sono nel formato *[NomeTabella][IdentificatoreRiga]*. Ad esempio `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifica una riga **\<** nel blocco ***DataInstance*** **>** come modificata. L'annotazione **hasChanges** può avere uno dei due valori seguenti:<br /><br /> **Inserito**<br /> Identifica una riga **Added.**<br /><br /> **Volta**<br /> Identifica una riga **modificata** che contiene una versione di riga **Original** nel blocco ** \<diffgr:before>.** Si noti che **le** righe eliminate avranno una versione di riga **Original** nel blocco ** \<diffgr:before>,** ma non sarà presente alcun elemento annotato nel **\<** blocco ***DataInstance.*** **>**|  
|**hasErrors**|Identifica una riga **\<** nel blocco ***DataInstance*** **>** con **RowError**. L'elemento error viene inserito nel blocco ** \<>diffgr:errors.**|  
|**Errore**|Contiene il testo di **RowError** per un particolare elemento nel ** \<blocco diffgr:errors>.**|  
  
 Quando legge o scrive il proprio contenuto come DiffGram, il tipo <xref:System.Data.DataSet> include ulteriori annotazioni. Nella tabella seguente vengono descritte queste annotazioni aggiuntive, definite nello spazio dei nomi **urn:schemas-microsoft-com:xml-msdata**.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**RowOrder**|Conserva l'ordine di riga dei dati originali e identifica l'indice di una riga in un particolare tipo <xref:System.Data.DataTable>.|  
|**Nascosto**|Identifica una colonna come se una proprietà **ColumnMapping sia** impostata su **MappingType.Hidden**. L'attributo viene scritto nel formato **msdata:hidden** *[NomeColonna]**"" valore*". Ad esempio `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Notare che le colonne nascoste vengono scritte come attributo DiffGram solo se in tali colonne sono presenti dati. In caso contrario, vengono ignorate.|  
  
## <a name="sample-diffgram"></a>Esempio di DiffGram  
 Di seguito viene riportato un esempio di formato DiffGram. Questo esempio mostra il risultato di un aggiornamento a una riga prima della conferma delle modifiche. La riga con CustomerID pari a "ALFKI" è stata modificata, ma non aggiornata. Di conseguenza, è presente una riga **Current** con un **diffgr:id** **\<** di "Customers1" nel blocco ***DataInstance*** **>** e una riga **Original** con un **diffgr:id** di "Customers1" nel blocco ** \<diffgr:before>.** La riga con un CustomerID di "ANATR" include un **RowError**, pertanto viene annotato con `diffgr:hasErrors="true"` ed è presente un elemento correlato nel ** \<blocco diffgr:errors>.**  
  
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

- [Utilizzo di XML in un dataset](using-xml-in-a-dataset.md)
- [Caricamento di un dataset da XML](loading-a-dataset-from-xml.md)
- [Scrittura del contenuto di dataset come dati XML](writing-dataset-contents-as-xml-data.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
