---
title: <list>
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
ms.openlocfilehash: db5c571d2f2c59419c886f6596f4e4dbd30d7baf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352314"
---
# <a name="list-visual-basic"></a>elenco di \<> (Visual Basic)
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
 Tipo dell'elenco. Deve essere un "Bullet" per un elenco puntato, "Number" per un elenco numerato o "Table" per una tabella a due colonne.  
  
 `term`  
 Utilizzato solo quando `type` è "Table". Termine da definire, definito nel tag Description.  
  
 `description`  
 Quando `type` è "Bullet" o "Number", `description` è un elemento nell'elenco quando `type` è "Table" `description` è la definizione di `term`.  
  
## <a name="remarks"></a>Osservazioni  
 Il blocco `<listheader>` definisce l'intestazione di un elenco di tabelle o di definizioni. Quando si definisce una tabella, è necessario specificare solo una voce per `term` nell'intestazione.  
  
 Ogni elemento nell'elenco viene specificato con un blocco `<item>`. Quando si crea un elenco di definizioni, è necessario specificare sia `term` sia `description`. Tuttavia, per una tabella, un elenco puntato o un elenco numerato, è necessario specificare solo una voce per `description`.  
  
 Un elenco o una tabella può contenere il numero di blocchi di `<item>` necessari.  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il tag `<list>` per definire un elenco puntato nella sezione Osservazioni.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
