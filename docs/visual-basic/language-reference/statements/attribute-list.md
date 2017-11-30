---
title: Elenco degli attributi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a>Elenco degli attributi (Visual Basic)
Specifica gli attributi da applicare a un elemento di programmazione dichiarato. Gli attributi sono separati da una virgola. Di seguito è la sintassi per un attributo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Parti  
 `attributemodifier`  
 Obbligatorio per gli attributi applicati all'inizio di un file di origine. Può essere [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) o [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Obbligatorio. Nome dell'attributo.  
  
 `attributearguments`  
 Parametro facoltativo. Elenco di argomenti posizionali per questo attributo. Più argomenti sono separati da virgole.  
  
 `attributeinitializer`  
 Parametro facoltativo. Elenco di inizializzatori di variabile o proprietà per questo attributo. Gli inizializzatori sono separati da virgole.  
  
## <a name="remarks"></a>Note  
 È possibile applicare uno o più attributi a qualsiasi elemento di programmazione (tipi, procedure, le proprietà e così via). Gli attributi vengono visualizzati nei metadati dell'assembly e consentono di annotare il codice o specificare l'utilizzo di un particolare elemento di programmazione. È possibile applicare attributi definiti da Visual Basic e .NET Framework, ed è possibile definire attributi personalizzati.  

 Per ulteriori informazioni sull'utilizzo degli attributi, vedere [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md). Per informazioni sui nomi degli attributi, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regole  
  
-   **Selezione host.** È possibile applicare attributi a dichiarato più elementi di programmazione. Per applicare uno o più attributi, posizionare un *blocco di attributi* all'inizio della dichiarazione dell'elemento. Ogni voce nell'elenco degli attributi specifica un attributo che si desidera applicare, e il modificatore e gli argomenti utilizzati per la chiamata dell'attributo.  
  
-   **Parentesi angolari.** Se si fornisce un elenco di attributi, è necessario racchiuderlo tra parentesi quadre ("`<`"e"`>`").  
  
-   **Parte della dichiarazione.** L'attributo deve essere parte della dichiarazione di elemento, non un'istruzione separata. È possibile utilizzare la sequenza di continuazione di riga (" `_`") per estendere l'istruzione di dichiarazione su più righe di codice sorgente.  
  
-   **Modificatori.** Un modificatore di attributo (`Assembly` o `Module`) è necessaria per ogni attributo applicato a un elemento di programmazione all'inizio di un file di origine. Attributo modificatori non consentiti per gli attributi applicati agli elementi che non si trovano all'inizio di un file di origine.  
  
-   **Argomenti.** Tutti gli argomenti posizionali per un attributo devono precedere gli inizializzatori di qualsiasi variabile o proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene applicato il <xref:System.Runtime.InteropServices.DllImportAttribute> dell'attributo a una struttura di definizione di un `Function` stored procedure.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>indica che la routine con attributi rappresenta un punto di ingresso in una libreria di collegamento dinamico (DLL) non gestita. L'attributo fornisce il nome della DLL come un argomento posizionale e le altre informazioni come inizializzatori.  
  
## <a name="see-also"></a>Vedere anche  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [Modulo \<parola chiave>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
