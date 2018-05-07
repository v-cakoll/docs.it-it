---
title: Mapping esterno
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 640dff5555ab346782825c44ded758a681226648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="external-mapping"></a>Mapping esterno
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta *mapping esterno*, un processo mediante il quale è possibile utilizzare un file XML separato per specificare il mapping tra il modello di dati del database e il modello a oggetti. I vantaggi dell'uso di un file di mapping esterno sono:  
  
-   È possibile evitare di includere il codice di mapping nel codice dell'applicazione. Questo approccio evita confusione nel codice dell'applicazione.  
  
-   Un file di mapping esterno è simile a un file di configurazione. Ad esempio, è possibile aggiornare il modo in cui l'applicazione si comporta dopo avere fornito i file binari semplicemente eseguendo lo swapping del file di mapping esterno.  
  
## <a name="requirements"></a>Requisiti  
 Il file di mapping deve essere un file XML e il file deve convalidare un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] file schema definition (XSD).  
  
 È necessario attenersi alle regole che seguono:  
  
-   Il file di mapping deve essere un file XML.  
  
-   Il file di mapping XML deve essere convalidato in base al file di definizione di XML Schema. Per ulteriori informazioni, vedere [come: il file di Mapping esterni e DBML di convalidare](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).  
  
-   Il mapping esterno esegue l'override del mapping basato sugli attributi. In altre parole, quando si usa un'origine del mapping esterna per creare un oggetto <xref:System.Data.Linq.DataContext>, <xref:System.Data.Linq.DataContext> ignora tutti gli attributi di mapping creati nelle classi. Questo comportamento si verifica se la classe è inclusa nel file di mapping esterno.  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta l'uso ibrido dei due approcci del mapping (esterno e basato sugli attributi).  
  
## <a name="xml-schema-definition-file"></a>File di definizione di XML Schema  
 Il mapping esterno in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deve essere convalidato in base alla seguente definizione di XML Schema.  
  
 È necessario distinguere questo file di definizione dello schema dal file di definizione dello schema usato per convalidare un file DBML. Per ulteriori informazioni, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)).  
  
> [!NOTE]
>  Gli utenti di Visual Studio verranno anche trovare questo file XSD nella finestra di dialogo XML Schema come "LinqToSqlMapping". Per usare correttamente il file per la convalida di un file di mapping esterno, vedere [come: file di Mapping esterni e DBML di convalidare](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).  
  
```  
?<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [Procedura: generare il modello a oggetti come file esterno](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)
