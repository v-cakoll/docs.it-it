---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0d1b03d9ab98f28a0112198f1ecc1e928d6d4a7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408712"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
Definisce le costanti del compilatore condizionali.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

Oppure

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`symbol`|Obbligatorio. Il simbolo da definire.|  
|`value`|Facoltativa. Il valore da assegnare a `symbol`. Se `value` è una stringa, deve essere racchiusa tra sequenze di barre rovesciate o virgolette ( \\ ") anziché virgolette. Se non è specificato un valore, è considerato True.|  
  
## <a name="remarks"></a>Commenti  
 L' `-define` opzione ha un effetto simile all'uso di una `#Const` direttiva per il preprocessore nel file di origine, ad eccezione del fatto che le costanti definite con `-define` sono pubbliche e si applicano a tutti i file nel progetto.  
  
 È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.  
  
 `-d` è la versione abbreviata di `-define`.  
  
 È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.  
  
|Per impostare-define in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **Compila** .<br />3. fare clic su **Avanzate**.<br />4. modificare il valore nella casella **costanti personalizzate** .|  
  
## <a name="example"></a>Esempio  
 Nel codice seguente sono definite e usate due costanti di compilazione condizionale.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [#If... Direttive then... #Else](../../language-reference/directives/if-then-else-directives.md)
- [#Const (direttiva)](../../language-reference/directives/const-directive.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
