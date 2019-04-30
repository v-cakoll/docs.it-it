---
title: Supporto dell'ereditarietà
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 668f4f1dd284550e644ce6b8a4491ca47105575e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033553"
---
# <a name="inheritance-support"></a><span data-ttu-id="dbeaa-102">Supporto dell'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="dbeaa-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="dbeaa-103">supporta *mapping di singole tabelle*.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-103">supports *single-table mapping*.</span></span> <span data-ttu-id="dbeaa-104">In altre parole, una gerarchia di ereditarietà completa viene archiviata in un'unica tabella di database,</span><span class="sxs-lookup"><span data-stu-id="dbeaa-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="dbeaa-105">che contiene l'unione bidimensionale di tutte le possibili colonne di dati per l'intera gerarchia.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="dbeaa-106">Un'unione è il risultato della combinazione di due tabelle in una sola contenente le righe presenti in ciascuna delle tabelle originali. In ogni riga è indicato un valore null in corrispondenza delle colonne non applicabili al tipo dell'istanza rappresentata dalla riga stessa.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="dbeaa-107">La strategia di mapping di singole tabelle è la più semplice rappresentazione di ereditarietà e offre caratteristiche di prestazioni ottimali per numerose categorie di query.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="dbeaa-108">Per implementare questo tipo di mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è necessario specificare gli attributi e le relative proprietà sulla classe radice della gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="dbeaa-109">Per altre informazioni, vedere [Procedura: Eseguire il mapping di gerarchie di ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="dbeaa-109">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="dbeaa-110">Gli sviluppatori che usano Visual Studio consente inoltre di [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping delle gerarchie di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="dbeaa-110">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbeaa-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbeaa-111">See also</span></span>

- [<span data-ttu-id="dbeaa-112">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="dbeaa-112">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
