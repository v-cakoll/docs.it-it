---
title: Annotazioni LINQ to XML
description: Informazioni su come usare le annotazioni in LINQ to XML per associare qualsiasi oggetto arbitrario di qualsiasi tipo arbitrario a qualsiasi componente XML in un albero XML.
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: e7da666139c10b26de37816693202d96498f52d8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165577"
---
# <a name="linq-to-xml-annotations"></a>Annotazioni LINQ to XML

Le annotazioni in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono di associare qualsiasi oggetto arbitrario di qualsiasi tipo arbitrario a qualsiasi componente XML di un albero XML.

Per aggiungere un'annotazione a un componente XML, ad esempio <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, viene chiamato il metodo <xref:System.Xml.Linq.XObject.AddAnnotation%2A>. Le annotazioni vengono recuperate in base al tipo.

Si noti che le annotazioni non fanno parte dell'infoset XML; non sono serializzate né deserializzate.

## <a name="methods"></a>Metodi

Con le annotazioni è possibile usare i metodi seguenti:

|Metodo|Descrizione|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Consente di aggiungere un oggetto all'elenco di annotazioni di un oggetto <xref:System.Xml.Linq.XObject>.|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Consente di ottenere il primo oggetto annotazione del tipo specificato da un oggetto <xref:System.Xml.Linq.XObject>.|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Consente di ottenere una raccolta di annotazioni del tipo specificato per un oggetto <xref:System.Xml.Linq.XObject>.|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Consente di rimuove le annotazioni del tipo specificato da un oggetto <xref:System.Xml.Linq.XObject>.|
