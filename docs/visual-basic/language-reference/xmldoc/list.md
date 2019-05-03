---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 7d7b85867f4c701322c5e6c31f2d89ab38fad05d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940878"
---
# <a name="list-visual-basic"></a>\<list> (Visual Basic)
Definisce un elenco o una tabella.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
## <a name="parameters"></a>Parametri  
 `type`  
 Il tipo dell'elenco. Deve essere un "punto elenco" per un elenco puntato, "number" per un elenco numerato o "table" per una tabella a due colonne.  
  
 `term`  
 Usato solo `type` è "table". Termine da definire, che viene definito nel tag di descrizione.  
  
 `description`  
 Quando `type` è "bullet" o "number", `description` è un elemento nell'elenco quando `type` è "table" `description` è la definizione di `term`.  
  
## <a name="remarks"></a>Note  
 Il `<listheader>` blocco definisce l'intestazione di tabella o una definizione elenco. Quando si definisce una tabella, è sufficiente fornire una voce per `term` nell'intestazione.  
  
 Ogni elemento nell'elenco viene specificato con un `<item>` blocco. Quando si crea un elenco di definizioni, è necessario specificare entrambe `term` e `description`. Tuttavia, per una tabella, elenco puntato o numerato, è sufficiente fornire una voce per `description`.  
  
 Un elenco o una tabella può avere un numero `<item>` blocca in base alle esigenze.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `<list>` tag per definire un elenco puntato nella sezione Osservazioni.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
