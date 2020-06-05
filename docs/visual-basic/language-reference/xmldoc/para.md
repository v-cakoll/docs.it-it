---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400073"
---
# <a name="para-visual-basic"></a><span data-ttu-id="40dc2-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40dc2-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="40dc2-102">Specifica che il contenuto è formattato come paragrafo.</span><span class="sxs-lookup"><span data-stu-id="40dc2-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40dc2-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40dc2-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="40dc2-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="40dc2-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="40dc2-105">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="40dc2-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40dc2-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="40dc2-106">Remarks</span></span>  
 <span data-ttu-id="40dc2-107">Il `<para>` tag è da usare all'interno di un tag, ad esempio [\<summary>](summary.md) , [\<remarks>](remarks.md) o [\<returns>](returns.md) , e consente di aggiungere la struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="40dc2-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="40dc2-108">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="40dc2-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40dc2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="40dc2-109">Example</span></span>  
 <span data-ttu-id="40dc2-110">Questo esempio usa il `<para>` tag per suddividere la sezione Osservazioni per il `UpdateRecord` metodo in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="40dc2-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="40dc2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40dc2-111">See also</span></span>

- [<span data-ttu-id="40dc2-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="40dc2-112">XML Comment Tags</span></span>](index.md)
