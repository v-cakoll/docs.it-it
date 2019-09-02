---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 29b905c42f15cad4eb8521c4d702b56093982445
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203785"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivazione della struttura relazionale di dataset da XML Schema (XSD)
Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language). In generale, per ogni `complexType` elemento figlio di un elemento dello schema, viene generata una tabella `DataSet`in. La struttura della tabella è determinata dalla definizione del tipo complesso. Le `DataSet` tabelle vengono create in per gli elementi di primo livello nello schema. Tuttavia, una tabella viene creata solo per un elemento di livello `complexType` principale quando l' `complexType` elemento è annidato all' `complexType` interno di un altro elemento, nel `complexType` qual caso l'elemento `DataSet`annidato viene mappato a un oggetto `DataTable` all'interno di.  
  
 Per ulteriori informazioni su XSD, vedere la World Wide Web Consortium (W3C) [XML Schema Part 0: Raccomandazione](https://www.w3.org/TR/xmlschema-0/) principale[, XML Schema Part 1: Indicazioni](https://www.w3.org/TR/xmlschema-1/) sulle[strutture e XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/).  
  
 Nell'esempio seguente viene illustrato un XML schema `customers` in cui è l'elemento figlio `MyDataSet` dell'elemento, che è un elemento del **set di dati** .  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 L'elemento `customers` nell'esempio precedente è un elemento di tipo complesso. La definizione di tipo complesso viene quindi analizzata e la tabella seguente viene creata dal processo di mapping.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.  
  
> [!NOTE]
> Se l'elemento `customers` è di un tipo di dati XML Schema semplice, ad esempio **Integer**, non viene generata alcuna tabella. Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.  
  
 Nel seguente schema XML, l'elemento **schema** ha due elementi figlio, `InStateCustomers` e. `OutOfStateCustomers`  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`). Pertanto, il processo di mapping genera le due tabelle identiche seguenti `DataSet`in.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema usati per creare vincoli UNIQUE ed Foreign Key `DataSet`in un oggetto.  
  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne `DataSet`della tabella in un oggetto.  
  
 [Vincoli e relazioni di XML Schema](xml-schema-constraints-and-relationships.md)  
 Viene descritto come vengono create le relazioni in modo implicito quando si utilizzano gli elementi dello `DataSet`schema XML per creare vincoli in un oggetto.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](using-xml-in-a-dataset.md)  
 Viene descritto come caricare e salvare in modo permanente la struttura relazionale e `DataSet` i dati in un oggetto come dati XML.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
