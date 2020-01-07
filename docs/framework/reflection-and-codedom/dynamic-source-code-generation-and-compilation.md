---
title: Generazione e compilazione di codice sorgente dinamico
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
ms.openlocfilehash: 7379bac07de9b78369d3742fa3288f6fea6a573f
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544991"
---
# <a name="compile-and-generate-dynamic-source-code"></a>Compilare e generare codice sorgente dinamico

.NET Framework include un meccanismo denominato Code Document Object Model (CodeDOM) che consente agli sviluppatori di programmi che creano codice sorgente di generarlo, in fase di esecuzione, in più linguaggi di programmazione in base a un unico modello che rappresenta il codice da generare.  
  
Per rappresentare il codice sorgente, gli elementi CodeDOM vengono collegati tra loro per formare una struttura di dati nota come grafico CodeDOM che modella la struttura del codice sorgente.  
  
Lo spazio dei nomi <xref:System.CodeDom?displayProperty=fullName> definisce i tipi che possono rappresentare la struttura logica del codice sorgente, in modo indipendente da un linguaggio di programmazione specifico. Lo spazio dei nomi <xref:System.CodeDom.Compiler?displayProperty=fullName> definisce i tipi per la generazione di codice sorgente a partire dai grafici CodeDOM e la gestione della compilazione del codice sorgente nei linguaggi supportati. I produttori di compilatori o gli sviluppatori possono estendere il set di linguaggi supportati.  
  
La modellazione di codice sorgente indipendente da uno specifico linguaggio si rivela particolarmente utile quando occorre che un programma generi codice sorgente per un modello di programma in più linguaggi o in un linguaggio di destinazione non ancora definito. Alcuni progettisti usano ad esempio CodeDOM come interfaccia indipendente dal linguaggio per produrre codice sorgente nel linguaggio di programmazione desiderato, ove sia disponibile il supporto CodeDOM per il linguaggio.  
  
.NET Framework include generatori di codice e compilatori di codice per i seguenti linguaggi: <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> e <xref:Microsoft.VisualBasic.VBCodeProvider>.  
  
## <a name="in-this-section"></a>In questa sezione

- [Uso di CodeDOM](using-the-codedom.md)

  Vengono descritti gli usi più comuni e viene illustrata la compilazione di un semplice oggetto grafico mediante l'uso di CodeDOM.  
  
- [Generare codice sorgente e compilare un programma da un grafo CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md)  

  Viene descritto come generare codice sorgente e compilare il codice generato con un compilatore esterno usando le classi definite nello spazio dei nomi `System.CodeDom.Compiler`.  
  
- [How to: Create an XML Documentation File Using CodeDOM](how-to-create-an-xml-documentation-file-using-codedom.md) (Procedura: Creare un file di documentazione XML tramite CodeDOM)  

  Viene descritto come usare CodeDOM per generare codice con commenti di documentazione XML e come compilare il codice generato in modo da creare l'output della documentazione XML.  
  
- [Procedura: Creare una classe tramite CodeDOM](how-to-create-a-class-using-codedom.md)  

  Viene descritto come usare CodeDOM per generare una classe contenente campi, proprietà, un metodo, un costruttore e un punto di ingresso.  
  
## <a name="reference"></a>Riferimenti  

- <xref:System.CodeDom>  

  Definisce elementi che rappresentano elementi di codice in linguaggi di programmazione che si avvalgono del Common Language Runtime.  
  
- <xref:System.CodeDom.Compiler>  

  Definisce le interfacce per la generazione e la compilazione di codice in fase di esecuzione.  
  
## <a name="related-sections"></a>Sezioni correlate  

- Il [riferimento rapido per CodeDom](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) fornisce agli sviluppatori un modo rapido per trovare gli elementi CodeDOM che rappresentano gli elementi del codice sorgente.
