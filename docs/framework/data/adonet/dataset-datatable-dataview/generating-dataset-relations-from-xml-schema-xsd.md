---
title: Generazione di relazioni tra dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: b74c992c4569512a8692b70663002fd609d3501e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546139"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generazione di relazioni tra dataset da XML Schema (XSD)
In un tipo <xref:System.Data.DataSet> è possibile stabilire un'associazione tra due o più colonne creando una relazione padre-figlio. Esistono tre modi per rappresentare un **set di dati** relazione all'interno di uno schema di XML Schema definition language (XSD):  
  
-   Specificare tipi complessi annidati.  
  
-   Usare la **msdata: Relationship** annotazione.  
  
-   Specificare un **xs: keyref** senza il **msdata: ConstraintOnly** annotazione.  
  
## <a name="nested-complex-types"></a>Tipi complessi annidati  
 Le definizioni di tipi complessi annidati in uno schema indicano le relazioni padre-figlio degli elementi. Il seguente frammento di XML Schema indica che **OrderDetail** è un elemento figlio delle **ordine** elemento.  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Il processo di mapping dello Schema XML crea tabelle i **set di dati** che corrispondono ai tipi complessi annidati nello schema. Crea anche colonne aggiuntive che vengono usate come elemento padre**-** colonne figlio per le tabelle generate. Si noti che questi padre**-** colonne figlio specificare relazioni, che non è la stessa funzione primari/chiave vincoli di chiave esterna.  
  
## <a name="msdatarelationship-annotation"></a>Annotazione msdata:Relationship  
 Il **msdata: Relationship** annotazione consente di specificare esplicitamente relazioni padre-figlio tra gli elementi nello schema che non sono annidati. L'esempio seguente mostra la struttura del **relazione** elemento.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Gli attributi del **msdata: Relationship** annotazione identificare gli elementi coinvolti nella relazione padre-figlio, nonché come le **vlastnosti parentkey** e **childkey** gli elementi e attributi coinvolti nella relazione. Il processo di mapping utilizza queste informazioni per generare le tabelle di **set di dati** e creare la relazione chiave primaria/esterna chiave tra le tabelle.  
  
 Ad esempio, il seguente frammento di schema specifica **ordine** e **OrderDetail** elementi allo stesso livello (non annidati). Lo schema specifica un **msdata: Relationship** annotazione, che specifica la relazione padre-figlio tra questi due elementi. In questo caso, deve essere specificata una relazione esplicita mediante il **msdata: Relationship** annotazione.  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 Il processo di mapping utilizza il **relazione** elemento per creare una relazione padre-figlio tra la **OrderNumber** colonna il **ordine** tabella e il **OrderNo** colonna il **OrderDetail** tabella il **set di dati**. Il processo di mapping consente solo di specificare la relazione. Non specifica automaticamente alcun vincolo sui valori di tali colonne, a differenza di quanto avviene mediante i vincoli di chiave primaria/chiave esterna nei database relazionali.  
  
### <a name="in-this-section"></a>In questa sezione  
 [Mapping di relazioni implicite tra elementi di schemi annidati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Descrive i vincoli e relazioni creati implicitamente in un **set di dati** quando sono presenti elementi annidati nello Schema XML.  
  
 [Mapping di relazioni specificate per elementi annidati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Viene descritto come impostare esplicitamente le relazioni un **set di dati** per gli elementi annidati di XML Schema.  
  
 [Specifica di relazioni tra elementi senza alcun annidamento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Viene descritto come creare le relazioni in un **set di dati** tra gli elementi di XML Schema che non sono annidati.  
  
### <a name="related-sections"></a>Sezioni correlate  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **set di dati** che viene creato da schema di XML Schema definition language (XSD).  
  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare i vincoli di chiave univoci ed esterni in una **set di dati**.  
  
## <a name="see-also"></a>Vedere anche
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
