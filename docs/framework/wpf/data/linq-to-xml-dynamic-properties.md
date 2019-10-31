---
title: Informazioni di riferimento sulle proprietà dinamiche LINQ to XML
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 48b51e92eb78786b2cc189e3e7daa00875b41585
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197047"
---
# <a name="linq-to-xml-dynamic-properties"></a>Proprietà dinamiche di LINQ to XML

Contenuto della sezione vengono fornite informazioni di riferimento relative alle proprietà dinamiche di LINQ to XML. In particolare, queste proprietà vengono esposte dalle classi <xref:System.Xml.Linq.XAttribute> e <xref:System.Xml.Linq.XElement>, incluse nello spazio dei nomi <xref:System.Xml.Linq>.

Come illustrato nell'argomento [Panoramica del data binding di WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), ogni proprietà dinamica è equivalente a una proprietà o a un metodo pubblico standard della stessa classe. Questi membri standard devono essere usati per la maggior parte degli scopi. Le proprietà dinamiche vengono fornite specificamente per gli scenari di associazione dati LINQ to XML. Per altre informazioni sui membri standard di queste classi, vedere gli argomenti di riferimento <xref:System.Xml.Linq.XAttribute> e <xref:System.Xml.Linq.XElement>.

Relativamente ai valori risolti, le proprietà dinamiche descritte in questa sezione rientrano in due categorie:

- Proprietà semplici, ad esempio le proprietà `Value` nelle classi <xref:System.Xml.Linq.XAttribute> e <xref:System.Xml.Linq.XElement>, che vengono risolte in un singolo valore.

- Valori indicizzati, ad esempio le proprietà [Elements](elements-xelement-dynamic-property.md) e [Descendants](descendants-xelement-dynamic-property.md) di <xref:System.Xml.Linq.XElement>, che vengono risolti in un tipo di indicizzatore. Affinché i tipi di indicizzatori vengano risolti nel valore o nella raccolta desiderata, è necessario passare un parametro di nome espanso.

Tutte le proprietà dinamiche che restituiscono un valore indicizzato di tipo <xref:System.Collections.Generic.IEnumerable%601> usano l'esecuzione posticipata. Per altre informazioni sull'esecuzione posticipata, vedere [Introduzione alle query LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="reference"></a>Reference

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a>Vedere anche

- [Associazione dati WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Panoramica del data binding WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Introduzione alle query LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
