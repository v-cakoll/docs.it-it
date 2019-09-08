---
title: Generazione di relazioni tra dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: d00f07ee3338941b7de1bb890f71cd3c2d120246
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784640"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generazione di relazioni tra dataset da XML Schema (XSD)
In un tipo <xref:System.Data.DataSet> è possibile stabilire un'associazione tra due o più colonne creando una relazione padre-figlio. Esistono tre modi per rappresentare una relazione del **set di dati** all'interno di uno schema XSD (XML Schema Definition Language):  
  
- Specificare tipi complessi annidati.  
  
- Usare l'annotazione **msdata: Relationship** .  
  
- Specificare **xs: keyref** senza l'annotazione **msdata: ConstraintOnly** .  
  
## <a name="nested-complex-types"></a>Tipi complessi annidati  
 Le definizioni di tipi complessi annidati in uno schema indicano le relazioni padre-figlio degli elementi. Il frammento di XML schema seguente mostra che **OrderDetail** è un elemento figlio dell'elemento **Order** .  
  
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
  
 Il processo di mapping di XML Schema consente di creare tabelle nel **DataSet** che corrispondono ai tipi complessi annidati nello schema. Vengono inoltre create altre colonne utilizzate come colonne padre **-** figlio per le tabelle generate. Si noti che queste **-** colonne padre-figlio specificano le relazioni, che non corrispondono alla specifica di vincoli di chiave primaria/chiave esterna.  
  
## <a name="msdatarelationship-annotation"></a>Annotazione msdata:Relationship  
 L'annotazione **msdata: Relationship** consente di specificare in modo esplicito le relazioni padre-figlio tra gli elementi dello schema che non sono annidati. Nell'esempio seguente viene illustrata la struttura dell'elemento **Relationship** .  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Gli attributi dell'annotazione **msdata: Relationship** identificano gli elementi che interessano la relazione padre-figlio, nonché gli elementi e gli attributi **ParentKey** e **childKEY** necessari per la relazione. Il processo di mapping utilizza queste informazioni per generare tabelle nel **set di dati** e per creare la relazione di chiave primaria/chiave esterna tra le tabelle.  
  
 Il frammento di schema seguente, ad esempio, specifica gli elementi **Order** e **OrderDetail** allo stesso livello (non annidato). Lo schema specifica un'annotazione **msdata: Relationship** , che specifica la relazione padre-figlio tra questi due elementi. In questo caso, è necessario specificare una relazione esplicita utilizzando l'annotazione **msdata: Relationship** .  
  
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
  
 Il processo di mapping usa l'elemento **Relationship** per creare una relazione padre-figlio tra la colonna **OrderNumber** nella tabella **Order** e la colonna **OrderNo** nella tabella **OrderDetail** del set di **dati**. Il processo di mapping consente solo di specificare la relazione. Non specifica automaticamente alcun vincolo sui valori di tali colonne, a differenza di quanto avviene mediante i vincoli di chiave primaria/chiave esterna nei database relazionali.  
  
### <a name="in-this-section"></a>In questa sezione  
 [Mapping di relazioni implicite tra elementi di schemi annidati](map-implicit-relations-between-nested-schema-elements.md)  
 Vengono descritti i vincoli e le relazioni creati in modo implicito in un **set di dati** quando gli elementi nidificati vengono rilevati in XML Schema.  
  
 [Mapping di relazioni specificate per elementi annidati](map-relations-specified-for-nested-elements.md)  
 Viene descritto come impostare in modo esplicito le relazioni in un **set di dati** per gli elementi annidati in XML Schema.  
  
 [Specifica di relazioni tra elementi senza alcun annidamento](specify-relations-between-elements-with-no-nesting.md)  
 Viene descritto come creare relazioni in un **set di dati** tra elementi XML Schema che non sono annidati.  
  
### <a name="related-sections"></a>Sezioni correlate  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **set di dati** creato dallo schema XSD (XML Schema Definition Language).  
  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema usati per creare vincoli UNIQUE ed Foreign Key in un **set di dati**.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../ado-net-overview.md)
