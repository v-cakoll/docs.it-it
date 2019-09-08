---
title: Supporto dell'ereditarietà
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 034aa6e75ca304d98aa4d3e1f3023c1a6940b73c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781562"
---
# <a name="inheritance-support"></a><span data-ttu-id="f54a0-102">Supporto dell'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="f54a0-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="f54a0-103">supporta il *mapping di una singola tabella*.</span><span class="sxs-lookup"><span data-stu-id="f54a0-103">supports *single-table mapping*.</span></span> <span data-ttu-id="f54a0-104">In altre parole, una gerarchia di ereditarietà completa viene archiviata in un'unica tabella di database,</span><span class="sxs-lookup"><span data-stu-id="f54a0-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="f54a0-105">che contiene l'unione bidimensionale di tutte le possibili colonne di dati per l'intera gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f54a0-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="f54a0-106">Un'unione è il risultato della combinazione di due tabelle in una sola contenente le righe presenti in ciascuna delle tabelle originali. In ogni riga è indicato un valore null in corrispondenza delle colonne non applicabili al tipo dell'istanza rappresentata dalla riga stessa.</span><span class="sxs-lookup"><span data-stu-id="f54a0-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="f54a0-107">La strategia di mapping di singole tabelle è la più semplice rappresentazione di ereditarietà e offre caratteristiche di prestazioni ottimali per numerose categorie di query.</span><span class="sxs-lookup"><span data-stu-id="f54a0-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="f54a0-108">Per implementare questo tipo di mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è necessario specificare gli attributi e le relative proprietà sulla classe radice della gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="f54a0-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="f54a0-109">Per altre informazioni, vedere [Procedura: Mappare le gerarchie](how-to-map-inheritance-hierarchies.md)di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="f54a0-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="f54a0-110">Gli sviluppatori che usano Visual Studio possono anche usare la Object Relational Designer per eseguire il mapping delle gerarchie di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="f54a0-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f54a0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f54a0-111">See also</span></span>

- [<span data-ttu-id="f54a0-112">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="f54a0-112">Background Information</span></span>](background-information.md)
