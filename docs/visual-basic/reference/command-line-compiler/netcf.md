---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: b64c55b73a9c835ded0d7c81ff36329b8d6a8bc9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586537"
---
# <a name="-netcf"></a>-netcf

Imposta il compilatore in modo che punti a [!INCLUDE[Compact](~/includes/compact-md.md)].

## <a name="syntax"></a>Sintassi

```
-netcf
```

## <a name="remarks"></a>Note

Il `-netcf` opzione fa sì che il compilatore Visual Basic alla destinazione di [!INCLUDE[Compact](~/includes/compact-md.md)] anziché la versione completa di .NET Framework. Funzionalità del linguaggio che è presente solo nella versione completa di .NET Framework è disabilitata.

Il `-netcf` opzione è progettata per essere usata con [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Le funzionalità del linguaggio per disabilitato `-netcf` sono le stesse funzionalità del linguaggio non è presente nel file di destinazione con `-sdkpath`.

> [!NOTE]
> Il `-netcf` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando. Il `-netcf` opzione viene impostata quando viene caricato un progetto di Visual Basic dispositivo.

Il `-netcf` opzione consente di modificare le funzionalità del linguaggio seguenti:

- Il [finali \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) parola chiave, che termina l'esecuzione di un programma, è disabilitato. Il programma seguente viene compilato ed eseguito senza `-netcf` ma non riesce in fase di compilazione con `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- L'associazione tardiva, in tutti i form, è disabilitato. Quando si verificano gli scenari di associazione tardiva riconosciuti, vengono generati errori in fase di compilazione. Il programma seguente viene compilato ed eseguito senza `-netcf` ma non riesce in fase di compilazione con `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- Il [automatica](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), e [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificatori sono disabilitati. La sintassi del [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) istruzione viene modificata anche a `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Il codice seguente illustra l'effetto di `-netcf` su una compilazione.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Utilizzo di parole chiave Visual Basic 6.0 che sono state rimosse da Visual Basic genera un errore diverso quando `-netcf` viene usato. Questo riguarda i messaggi di errore per le parole chiave seguenti:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Esempio

Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], con le versioni di mscorlib. dll e VisualBasic trovato nella directory di installazione predefinita del [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C. In genere, si utilizzerebbe la versione più recente del [!INCLUDE[Compact](~/includes/compact-md.md)].

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
