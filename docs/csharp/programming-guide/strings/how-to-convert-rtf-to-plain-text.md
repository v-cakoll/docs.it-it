---
title: 'Procedura: Convertire il formato RTF in testo normale (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting from RTF
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e4c7b48467f3b260526c604fa3a36fc5d80374e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a>Procedura: Convertire il formato RTF in testo normale (Guida per programmatori C#)
RTF (Rich Text Format) è un formato di documento sviluppato da Microsoft alla fine degli anni '80 per consentire lo scambio di documenti tra sistemi operativi. Sia Microsoft Word che WordPad sono in grado di leggere e scrivere documenti RTF. In .NET Framework è possibile usare il controllo <xref:System.Windows.Forms.RichTextBox> per creare un elaboratore di testo che supporti il formato RTF e consenta a un utente di applicare la formattazione al testo in modalità WYSIWIG.  
  
 È anche possibile usare il controllo <xref:System.Windows.Forms.RichTextBox> per rimuovere a livello di codice i codici di formattazione RTF da un documento e convertirlo in testo normale. Non è necessario incorporare il controllo in un Windows Form per eseguire questo tipo di operazione.  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a>Per usare il controllo RichTextBox in un progetto  
  
1.  Aggiungere un riferimento a System.Windows.Forms.dll.  
  
2.  Aggiungere una direttiva using per lo spazio dei nomi `System.Windows.Forms` (facoltativo).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente converte un file RTF di esempio in testo normale. Il file contiene formattazione RTF (ad esempio informazioni sul carattere), quattro caratteri Unicode e quattro caratteri ASCII estesi. Il codice di esempio apre il file, passa il suo contenuto a <xref:System.Windows.Forms.RichTextBox> in formato RTF, recupera il contenuto come testo, visualizza il testo in un oggetto <xref:System.Windows.Forms.MessageBox> e restituisce come output il testo in un file in formato UTF-8.  
  
 `MessageBox` e il file di output contengono il testo seguente:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 I caratteri RTF sono codificati in otto bit. Gli utenti possono però specificare caratteri Unicode in aggiunta ai caratteri ASCII estesi dalle tabelle codici specificate. Poiché la proprietà <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> è di tipo [string](../../../csharp/language-reference/keywords/string.md), i caratteri sono codificati come Unicode UTF-16. Tutti i caratteri ASCII estesi e i caratteri Unicode del documento RTF di origine vengono codificati correttamente nell'output di testo.  
  
 Se si usa il metodo <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> per scrivere il testo su disco, il testo sarà codificato come UTF-8 (senza byte order mark).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Stringhe](../../../csharp/programming-guide/strings/index.md)

