---
title: Generazione di relazioni tra dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: fdf22c311ef7b4267f4a4da8566e4ea59504b103
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generazione di relazioni tra dataset da XML Schema (XSD)
In un tipo <xref:System.Data.DataSet> è possibile stabilire un'associazione tra due o più colonne creando una relazione padre-figlio. Esistono tre modi per rappresentare un **DataSet** relazione all'interno di uno schema di XML Schema definition language (XSD):  
  
-   Specificare tipi complessi annidati.  
  
-   Utilizzare il **msdata: Relationship** annotazione.  
  
-   Specificare un **xs:** senza il **msdata: ConstraintOnly** annotazione.  
  
## <a name="nested-complex-types"></a>Tipi complessi annidati  
 Le definizioni di tipi complessi annidati in uno schema indicano le relazioni padre-figlio degli elementi. Il frammento di XML Schema seguente mostra che **OrderDetail** è un elemento figlio del **ordine** elemento.  
  
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
  
 Il processo di mapping di XML Schema consente di creare tabelle di **DataSet** che corrispondono ai tipi complessi annidati nello schema. Crea inoltre colonne aggiuntive che vengono utilizzate come padre**-** colonne figlio per le tabelle generate. Si noti che questi padre**-** colonne figlio di specificare relazioni, che non equivale a specificare vincoli di chiave esterna o chiave primaria.  
  
## <a name="msdatarelationship-annotation"></a>Annotazione msdata:Relationship  
 Il **msdata: Relationship** annotazione consente di specificare esplicitamente relazioni padre-figlio tra gli elementi dello schema che non sono annidati. L'esempio seguente mostra la struttura del **relazione** elemento.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Gli attributi del **msdata: Relationship** consentono di identificare gli elementi coinvolti nella relazione padre-figlio, nonché come il **parentkey** e **childkey** elementi e attributi coinvolti nella relazione. Il processo di mapping utilizza queste informazioni per generare le tabelle di **DataSet** e creare la relazione chiave primaria/esterna chiave tra le tabelle.  
  
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
  
 Il processo di mapping viene utilizzato il **relazione** elemento per creare una relazione padre-figlio tra il **OrderNumber** colonna il **ordine** tabella e il **OrderNo** colonna il **OrderDetail** tabella il **DataSet**. Il processo di mapping consente solo di specificare la relazione. Non specifica automaticamente alcun vincolo sui valori di tali colonne, a differenza di quanto avviene mediante i vincoli di chiave primaria/chiave esterna nei database relazionali.  
  
### <a name="in-this-section"></a>In questa sezione  
 [Mapping di relazioni implicite tra elementi di schemi annidati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Descrive i vincoli e le relazioni creati implicitamente in un **DataSet** quando sono presenti elementi annidati nello Schema XML.  
  
 [Mapping di relazioni specificate per elementi annidati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Viene descritto come impostare esplicitamente le relazioni un **DataSet** per gli elementi annidati nello Schema XML.  
  
 [Specifica di relazioni tra elementi senza alcun annidamento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Viene descritto come creare relazioni in un **DataSet** tra elementi di XML Schema che non sono annidati.  
  
### <a name="related-sections"></a>Sezioni correlate  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **DataSet** creato da uno schema XML Schema definition language (XSD).  
  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli di chiave esterni e univoci in un **DataSet**.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
