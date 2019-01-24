---
title: Elenco degli attributi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 9ab55187fef11fba9c794ff0266656860bea3d1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672110"
---
# <a name="attribute-list-visual-basic"></a>Elenco degli attributi (Visual Basic)
Specifica gli attributi da applicare a un elemento di programmazione dichiarato. Gli attributi sono separati da una virgola. Di seguito è la sintassi per un attributo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Parti  
|||
|---|---|
|`attributemodifier`|Obbligatorio per gli attributi applicati all'inizio di un file di origine. Può essere [assieme](../../../visual-basic/language-reference/modifiers/assembly.md) oppure [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Obbligatorio. Nome dell'attributo.|
|`attributearguments`|Facoltativo. Elenco di argomenti posizionali per questo attributo. Più argomenti sono separati da virgole.|
|`attributeinitializer`|Facoltativo. Elenco di inizializzatori di proprietà o variabile di questo attributo. Gli inizializzatori sono separati da virgole.|
  
## <a name="remarks"></a>Note  
 È possibile applicare uno o più attributi a qualsiasi elemento di programmazione (tipi, procedure, le proprietà e così via). Gli attributi vengono visualizzati nei metadati dell'assembly e usarli per annotare il codice o specificare l'utilizzo di un particolare elemento di programmazione. È possibile applicare attributi definiti da Visual Basic e .NET Framework, ed è possibile definire attributi personalizzati.  

 Per altre informazioni su quando usare gli attributi, vedere [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md). Per informazioni sui nomi degli attributi, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regole  
  
-   **Selezione host.** È possibile applicare attributi agli elementi di programmazione dichiarati più. Per applicare uno o più attributi, si inserisce un' *blocco di attributi* all'inizio della dichiarazione dell'elemento. Ogni voce nell'elenco degli attributi specifica un attributo che si desidera applicare, e il modificatore e gli argomenti utilizzati per la chiamata dell'attributo.  
  
-   **Parentesi quadre.** Se si fornisce un elenco di attributi, è necessario racchiuderlo tra parentesi angolari ("`<`"e"`>`").  
  
-   **Parte della dichiarazione.** L'attributo deve essere parte della dichiarazione di elemento, non un'istruzione separata. È possibile usare la sequenza di continuazione di riga (" `_`") per estendere l'istruzione di dichiarazione su più righe di codice sorgente.  
  
-   **Modificatori.** Un modificatore di attributo (`Assembly` o `Module`) è obbligatorio in tutti gli attributi applicati a un elemento di programmazione all'inizio di un file di origine. Attributo modificatori non consentiti per gli attributi applicati agli elementi che non sono all'inizio di un file di origine.  
  
-   **Argomenti.** Tutti gli argomenti posizionali per un attributo devono precedere tutti gli inizializzatori di proprietà o variabile.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente applica il <xref:System.Runtime.InteropServices.DllImportAttribute> dell'attributo a una struttura di definizione di un `Function` procedure.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> indica che la routine con attributi rappresenta un punto di ingresso in una libreria di collegamento dinamico (DLL) non gestita. L'attributo fornisce il nome della DLL come un argomento posizionale e le altre informazioni come gli inizializzatori di variabili.  
  
## <a name="see-also"></a>Vedere anche
- [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Modulo \<parola chiave>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
