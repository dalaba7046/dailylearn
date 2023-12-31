那天面試完之後，發現已經遺忘很多原本應該要知道的基礎知識
這幾天做個整理
首先是OOP(物件導向)，每次都會忘記英文應該的寫法，只記得叫物件導向

OOP(Object-oriented programming)

*封裝（Encapsulation）*
- **描述**：封裝是將數據（屬性）和行為（方法）組合在一起的過程。在封裝中，對象的內部狀態是從外部代碼隱藏的，並且只能通過該對象的方法來訪問。
- **應用場景**：
  - **數據隱藏**：例如，一個銀行帳戶對象可以隱藏其餘額細節，只允許通過存款和取款方法來修改。
  - **接口和實現分離**：在設計大型軟件系統時，開發者可以僅暴露必要的操作，而將內部邏輯保持私有。

*繼承（Inheritance）*
- **描述**：繼承允許一個類（子類）繼承另一個類（父類）的屬性和方法。子類可以擴展或修改繼承的屬性和方法。
- **應用場景**：
  - **代碼重用**：例如，可以有一個通用的「車輛」類，然後「汽車」、「卡車」和「摩托車」等子類可以繼承這個類的特性。
  - **建立層次結構**：在創建類別系統時，通過繼承建立一個清晰的層次結構，有助於理解和維護。

*多型（Polymorphism）*
- **描述**：多態性允許對象以多種形式呈現。在OOP中，多態性通常是通過重寫（方法覆蓋）和接口實現來實現的。
- **應用場景**：
  - **接口一致性**：例如，可以有一個「形狀」接口，具有「繪製」方法，而不同的形狀（如圓形、矩形）實現這個接口，但繪製方法的實現各不相同。
  - **靈活的代碼結構**：在設計時考慮到多態性，可以讓代碼更加靈活和可擴展，例如在設計一個渲染系統時，可以輕鬆地添加新的渲染類別而不影響現有代碼。
