---
title: Generazione di relazioni tra dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151130"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generazione di relazioni tra dataset da XML Schema (XSD)
In un tipo <xref:System.Data.DataSet> è possibile stabilire un'associazione tra due o più colonne creando una relazione padre-figlio. Esistono tre modi per rappresentare una relazione **DataSet** all'interno di uno schema XSD (XML Schema Definition Language):  
  
- Specificare tipi complessi annidati.  
  
- Utilizzare l'annotazione **msdata:Relationship.**  
  
- Specificare **un xs:keyref** senza l'annotazione **msdata:ConstraintOnly.**  
  
## <a name="nested-complex-types"></a>Tipi complessi annidati  
 Le definizioni di tipi complessi annidati in uno schema indicano le relazioni padre-figlio degli elementi. Il frammento XML Schema seguente mostra che **OrderDetail** è un elemento figlio del **Order** elemento.  
  
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
  
 Il processo di mapping dello schema XML crea tabelle nel **DataSet** che corrispondono ai tipi complessi annidati nello schema. Vengono inoltre create colonne aggiuntive**-** utilizzate come colonne figlio padre per le tabelle generate. Si noti**-** che queste colonne figlio padre specificano relazioni, che non corrisponde alla specifica di vincoli di chiave primaria/chiave esterna.  
  
## <a name="msdatarelationship-annotation"></a>Annotazione msdata:Relationship  
 L'annotazione **msdata:Relationship** consente di specificare in modo esplicito le relazioni padre-figlio tra gli elementi dello schema che non sono annidati. Nell'esempio seguente viene illustrata la struttura dell'elemento **Relationship.**  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 Gli attributi dell'annotazione **msdata:Relationship identificano** gli elementi coinvolti nella relazione padre-figlio, nonché gli elementi e gli attributi **parentkey** e **childkey** coinvolti nella relazione. Il processo di mapping utilizza queste informazioni per generare tabelle nel **DataSet** e per creare la relazione chiave primaria/chiave esterna tra queste tabelle.  
  
 Ad esempio, il frammento di schema seguente specifica **Order** e **OrderDetail** elementi allo stesso livello (non annidati). Lo schema specifica **un'annotazione msdata:Relationship,** che specifica la relazione padre-figlio tra questi due elementi. In questo caso, è necessario specificare una relazione esplicita utilizzando l'annotazione **msdata:Relationship.**  
  
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
  
 Il processo di mapping utilizza l'elemento **Relationship** per creare una relazione padre-figlio tra la colonna **OrderNumber** della tabella **Order** e la colonna **OrderNo** della tabella **OrderDetail** del **DataSet**. Il processo di mapping consente solo di specificare la relazione. Non specifica automaticamente alcun vincolo sui valori di tali colonne, a differenza di quanto avviene mediante i vincoli di chiave primaria/chiave esterna nei database relazionali.  
  
### <a name="in-this-section"></a>Contenuto della sezione  
 [Mapping di relazioni implicite tra elementi di schemi annidati](map-implicit-relations-between-nested-schema-elements.md)  
 Vengono descritti i vincoli e le relazioni creati in modo implicito in un **DataSet** quando gli elementi annidati vengono rilevati nello schema XML.  
  
 [Mapping di relazioni specificate per elementi annidati](map-relations-specified-for-nested-elements.md)  
 Viene descritto come impostare in modo esplicito le relazioni in un **DataSet** per gli elementi annidati nello schema XML.  
  
 [Specifica di relazioni tra elementi senza alcun annidamento](specify-relations-between-elements-with-no-nesting.md)  
 Viene descritto come creare relazioni in un **DataSet** tra elementi XML Schema non annidati.  
  
### <a name="related-sections"></a>Sezioni correlate  
 [Derivazione della struttura relazionale di dataset da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Viene descritta la struttura relazionale, o schema, di un **DataSet** creato dallo schema XSD (XML Schema Definition Language).  
  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi dello schema XML utilizzati per creare vincoli di chiave univoca ed esterna in un **DataSet**.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../ado-net-overview.md)
