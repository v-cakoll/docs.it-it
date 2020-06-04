---
title: 'Procedura: Leggere dati oggetto in un file XML'
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: 7097ec146987aea7855da40dd30f9cd3c17d8ce4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413167"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>Procedura: Leggere dati oggetto in un file XML (Visual Basic)
Questo esempio legge i dati oggetto scritti in precedenza in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Esempio  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Sostituire il nome di file "c:\temp\SerializationOverview.xml" con il nome del file contenente i dati serializzati. Per ulteriori informazioni sulla serializzazione dei dati, vedere [procedura: scrivere dati oggetto in un file XML (Visual Basic)](how-to-write-object-data-to-an-xml-file.md).  
  
 La classe deve avere un costruttore public senza parametri.  
  
 Solo le proprietà e i campi pubblici vengono deserializzati.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- La classe da serializzare non ha un costruttore pubblico senza parametri.  
  
- I dati nel file non rappresentano i dati della classe da deserializzare.  
  
- Il file non esiste (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Verificare sempre gli input e non deserializzare mai i dati proveniente da un'origine non attendibile. L'oggetto ricreato viene eseguito in un computer locale con le autorizzazioni del codice che ha eseguito la deserializzazione. Prima di usare i dati nell'applicazione verificare tutti gli input.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamWriter>
- [Procedura: Scrivere dati oggetto in un file XML (Visual Basic)](how-to-write-object-data-to-an-xml-file.md)
- [Serializzazione (Visual Basic)](index.md)
- [Guida per programmatori Visual Basic](../../index.md)
