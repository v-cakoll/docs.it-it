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
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a><span data-ttu-id="328dd-102">Procedura: Convertire il formato RTF in testo normale (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="328dd-102">How to: Convert RTF to Plain Text (C# Programming Guide)</span></span>
<span data-ttu-id="328dd-103">RTF (Rich Text Format) è un formato di documento sviluppato da Microsoft alla fine degli anni '80 per consentire lo scambio di documenti tra sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="328dd-103">Rich Text Format (RTF) is a document format developed by Microsoft in the late 1980s to enable the exchange of documents across operating systems.</span></span> <span data-ttu-id="328dd-104">Sia Microsoft Word che WordPad sono in grado di leggere e scrivere documenti RTF.</span><span class="sxs-lookup"><span data-stu-id="328dd-104">Both Microsoft Word and WordPad can read and write RTF documents.</span></span> <span data-ttu-id="328dd-105">In .NET Framework è possibile usare il controllo <xref:System.Windows.Forms.RichTextBox> per creare un elaboratore di testo che supporti il formato RTF e consenta a un utente di applicare la formattazione al testo in modalità WYSIWIG.</span><span class="sxs-lookup"><span data-stu-id="328dd-105">In the .NET Framework, you can use the <xref:System.Windows.Forms.RichTextBox> control to create a word processor that supports RTF and enables a user to apply formatting to text in a WYSIWIG manner.</span></span>  
  
 <span data-ttu-id="328dd-106">È anche possibile usare il controllo <xref:System.Windows.Forms.RichTextBox> per rimuovere a livello di codice i codici di formattazione RTF da un documento e convertirlo in testo normale.</span><span class="sxs-lookup"><span data-stu-id="328dd-106">You can also use the <xref:System.Windows.Forms.RichTextBox> control to programmatically remove the RTF formatting codes from a document and convert it to plain text.</span></span> <span data-ttu-id="328dd-107">Non è necessario incorporare il controllo in un Windows Form per eseguire questo tipo di operazione.</span><span class="sxs-lookup"><span data-stu-id="328dd-107">You do not need to embed the control in a Windows Form to perform this kind of operation.</span></span>  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a><span data-ttu-id="328dd-108">Per usare il controllo RichTextBox in un progetto</span><span class="sxs-lookup"><span data-stu-id="328dd-108">To use the RichTextBox control in a project</span></span>  
  
1.  <span data-ttu-id="328dd-109">Aggiungere un riferimento a System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="328dd-109">Add a reference to System.Windows.Forms.dll.</span></span>  
  
2.  <span data-ttu-id="328dd-110">Aggiungere una direttiva using per lo spazio dei nomi `System.Windows.Forms` (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="328dd-110">Add a using directive for the `System.Windows.Forms` namespace (optional).</span></span>  
  
## <a name="example"></a><span data-ttu-id="328dd-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="328dd-111">Example</span></span>  
 <span data-ttu-id="328dd-112">L'esempio seguente converte un file RTF di esempio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="328dd-112">The following example converts a sample RTF file to plain text.</span></span> <span data-ttu-id="328dd-113">Il file contiene formattazione RTF (ad esempio informazioni sul carattere), quattro caratteri Unicode e quattro caratteri ASCII estesi.</span><span class="sxs-lookup"><span data-stu-id="328dd-113">The file contains RTF formatting (such as font information), four Unicode characters, and four extended ASCII characters.</span></span> <span data-ttu-id="328dd-114">Il codice di esempio apre il file, passa il suo contenuto a <xref:System.Windows.Forms.RichTextBox> in formato RTF, recupera il contenuto come testo, visualizza il testo in un oggetto <xref:System.Windows.Forms.MessageBox> e restituisce come output il testo in un file in formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="328dd-114">The example code opens the file, passes its content to a <xref:System.Windows.Forms.RichTextBox> as RTF, retrieves the content as text, displays the text in a <xref:System.Windows.Forms.MessageBox>, and outputs the text to a file in UTF-8 format.</span></span>  
  
 <span data-ttu-id="328dd-115">`MessageBox` e il file di output contengono il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="328dd-115">The `MessageBox` and the output file contain the following text:</span></span>  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 <span data-ttu-id="328dd-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="328dd-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span></span>  
  
 <span data-ttu-id="328dd-117">I caratteri RTF sono codificati in otto bit.</span><span class="sxs-lookup"><span data-stu-id="328dd-117">RTF characters are encoded in eight bits.</span></span> <span data-ttu-id="328dd-118">Gli utenti possono però specificare caratteri Unicode in aggiunta ai caratteri ASCII estesi dalle tabelle codici specificate.</span><span class="sxs-lookup"><span data-stu-id="328dd-118">However, users can specify Unicode characters in addition to extended ASCII characters from specified code pages.</span></span> <span data-ttu-id="328dd-119">Poiché la proprietà <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> è di tipo [string](../../../csharp/language-reference/keywords/string.md), i caratteri sono codificati come Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="328dd-119">Because the <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> property is of type [string](../../../csharp/language-reference/keywords/string.md), the characters are encoded as Unicode UTF-16.</span></span> <span data-ttu-id="328dd-120">Tutti i caratteri ASCII estesi e i caratteri Unicode del documento RTF di origine vengono codificati correttamente nell'output di testo.</span><span class="sxs-lookup"><span data-stu-id="328dd-120">Any extended ASCII characters and Unicode characters from the source RTF document are correctly encoded in the text output.</span></span>  
  
 <span data-ttu-id="328dd-121">Se si usa il metodo <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> per scrivere il testo su disco, il testo sarà codificato come UTF-8 (senza byte order mark).</span><span class="sxs-lookup"><span data-stu-id="328dd-121">If you use the <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> method to write the text to disk, the text will be encoded as UTF-8 (without a Byte Order Mark).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328dd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="328dd-122">See Also</span></span>  
 <span data-ttu-id="328dd-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="328dd-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span></span>   
 [<span data-ttu-id="328dd-124">Stringhe</span><span class="sxs-lookup"><span data-stu-id="328dd-124">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

