# SwiftUI Journal Entry App Detail View
Improving the view that is opened once you select the title of the Journal Entry you want to see<br>
![journalentrydetailview](https://github.com/danielurra/Swift-UI-Journal-Entry-App-Detail-View/assets/51704179/b10b6166-c5f2-4cfd-8095-e82f43b21900)

## Grab the code - List View file
```swift

import SwiftUI

struct JournalEntriesListView: View {
    
    
    
    var body: some View {
        NavigationStack {
            List (plural){ iterateArrayMembers in
                NavigationLink(destination: JournalEntryDDetailView(detailJournalEntry: iterateArrayMembers)){
                    Text(iterateArrayMembers.title)
                }
            }
            .navigationTitle("\(plural.count) Journal Entries")
        }
    }
}

#Preview {
    JournalEntriesListView()
}

```
## Grab the code - jedi(class) file
```swift
//
//  jedi.swift
//  JournalEntries
//
//  Created by Eusebio Taba on 3/20/24.


import Foundation

class jedi: Identifiable { // jedi = journal entry dani individual (the blueprint)
    var title: String = ""
    var depunoyletra: String = ""
    var rating: Int = 1
    var timestamp: Date = Date()

    
    init(title: String, depunoyletra: String, rating: Int, timestamp: Date) {
        self.title = title
        self.depunoyletra = depunoyletra
        self.rating = rating
        self.timestamp = timestamp
    }
}

let plural: [jedi] = [
    jedi(title: "A great gold day", depunoyletra: "I found a nice pot of gold, I'm rich I tell ya!! Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.", rating: 3, timestamp: Date()),
    jedi(title: "Headache", depunoyletra: "I woke up with a headache and it never got well :/ Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.", rating: 1, timestamp: Date()),
    jedi(title: "My App is live!", depunoyletra: "I uploaded my first app to Apple store Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.", rating: 5, timestamp: Date()),
]
```
## Grab the code - Detail View file
You can add `emojis` by using the following key combination:<br>
* Ctrl + Command + Space bar<br>
![Screenshot 2024-03-22 at 6 34 44 AM](https://github.com/danielurra/Swift-UI-Journal-Entry-App-Detail-View/assets/51704179/49c01cb4-3df3-40ab-a790-d976d0743446)<br>
```swift
//
//  JournalEntryDannyDetailView.swift
//  JournalEntries
//
//  Created by Eusebio Taba on 3/22/24.
//

import SwiftUI

struct JournalEntryDDetailView: View {
    
    let detailJournalEntry: jedi
    
    var body: some View {
        ScrollView {
            VStack (alignment: .leading) {
                HStack {
                    Text(detailJournalEntry.timestamp, style: .date)
                        .bold()
                    Text(" - ")
                    Text(String(String(repeating: "⭐️", count: detailJournalEntry.rating)))
                }
                .padding(.bottom)
                Text(detailJournalEntry.depunoyletra)
                    .bold()
            }
            .padding()
        }
        .navigationTitle(detailJournalEntry.title)
    }
}

#Preview {
    NavigationStack {
        JournalEntryDDetailView(detailJournalEntry: jedi(title: "A great gold day", depunoyletra: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce fermentum elit eget ante pellentesque viverra. Aenean porttitor, augue at faucibus sagittis, nulla nisi venenatis ex, nec semper enim odio vel erat. Donec ut lacus volutpat, mattis lectus non, porttitor orci. Suspendisse arcu risus, lacinia feugiat odio eu, pulvinar consequat lacus. Ut tincidunt iaculis mi, sit amet euismod est fermentum sed. Nunc ullamcorper eget lectus eu pulvinar. Morbi efficitur mattis ipsum vel malesuada. Morbi nec justo nulla. Fusce auctor, nunc quis pellentesque scelerisque, arcu ligula finibus felis, eget consectetur nunc nibh sit amet eros. Aenean gravida faucibus nisl id egestas. Fusce lacinia et nunc et aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Integer non bibendum erat. Morbi lobortis sem a tellus sodales cursus. Quisque feugiat convallis volutpat. Cras sed nulla tortor.Phasellus egestas a leo accumsan laoreet. Nunc id sem leo. Praesent at sem nisl. Nulla dolor leo, consequat id maximus sed, accumsan at nibh. Vestibulum varius semper mauris eu lacinia. Duis vitae iaculis erat. Integer mollis augue felis, non mollis ligula fermentum eget. Nullam cursus facilisis lacus eget sollicitudin. Praesent consectetur accumsan magna ac bibendum. In mattis placerat commodo. Etiam in efficitur nisi, id eleifend metus. Ut porttitor nibh sed varius efficitur. Nulla non suscipit risus.Vivamus eleifend interdum odio eget viverra. Aliquam suscipit varius odio non sollicitudin. Nulla vel congue ligula. Nunc tristique scelerisque nisi non congue. Aenean non congue ligula. Integer efficitur urna in lorem suscipit, sed condimentum libero maximus. Sed posuere posuere ex ut tincidunt. Etiam vitae molestie elit.Cras a scelerisque mauris. Suspendisse nec massa risus. Sed feugiat purus eget risus fringilla porta. Suspendisse ornare sed eros quis lobortis. Sed semper interdum tincidunt. Donec nunc magna, efficitur nec gravida eget, pretium in arcu. Suspendisse dolor erat, eleifend eu ullamcorper et, porta et elit. Suspendisse faucibus leo eu arcu tincidunt suscipit. Donec pretium commodo dui vitae aliquam. Maecenas venenatis sit amet mi quis vestibulum. Proin sed eros elit. Suspendisse posuere vestibulum arcu eu molestie. Maecenas vulputate dolor vel aliquam facilisis. Nunc ac facilisis dolor. Duis ornare odio sapien, lobortis fermentum velit cursus vel.Donec metus orci, facilisis sodales auctor a, pulvinar sed est. Vestibulum tempus finibus massa, eget fringilla mi sollicitudin at. Integer laoreet urna purus, mattis pharetra nibh tempor non. Proin fringilla risus ac porta lacinia. Nunc viverra nibh lorem, luctus egestas ipsum placerat ac. Duis eu mi non mi venenatis convallis. Aenean diam risus, pharetra a volutpat ac, faucibus sit amet odio. Donec ac convallis mauris. Phasellus rhoncus elementum neque in interdum. Quisque dolor purus, fringilla quis mollis lacinia, efficitur a risus. Mauris vel eros ipsum. Phasellus iaculis ante sem, eu auctor lacus cursus eget. Donec viverra est id turpis rhoncus, eget ultrices ex luctus.Sed ipsum velit, auctor sed justo et, auctor sodales est. Nam fringilla quam volutpat imperdiet elementum. Nullam scelerisque condimentum suscipit. Etiam gravida quam vitae sem tristique rhoncus. Nam rutrum ante sem, id mattis orci porta pharetra. Pellentesque porttitor est in diam convallis, ac scelerisque eros fringilla. Nunc mauris quam, mollis ac augue ac, lobortis viverra turpis. Donec ac dolor quam. Nullam quis consectetur mi. Integer volutpat neque eget mi ullamcorper, in tempus metus auctor. Duis vehicula ligula eget ex sagittis molestie. Integer eget tortor erat. Donec eleifend non metus vel sagittis. Morbi commodo porta erat a tincidunt. Curabitur velit sapien, pulvinar ac enim ac, condimentum convallis lectus.Nunc id dapibus sem. Nam hendrerit, est sed cursus commodo, odio tortor rutrum libero, quis gravida urna quam nec dui. Nullam posuere commodo tortor, eu rutrum arcu. Etiam mollis ex tortor, ac dictum magna aliquet sit amet. Nulla gravida accumsan felis, sit amet vestibulum justo ultricies eu. Nulla enim leo, scelerisque at velit nec, facilisis maximus arcu. Aenean tempor maximus condimentum. Praesent eleifend sed purus nec volutpat. Phasellus vestibulum erat sed odio ultricies sodales. Quisque fermentum hendrerit molestie. Donec turpis leo, semper iaculis felis commodo, mattis faucibus purus. Cras condimentum felis orci, in volutpat velit maximus sit amet. Nunc ipsum libero, luctus consequat elementum eu, aliquet non mi. Ut bibendum euismod mauris, vel suscipit eros condimentum eget.Proin ac sem nec nunc congue mollis feugiat a sem. Vestibulum id lacus metus. Nam posuere tortor tellus, fringilla lobortis sem placerat a. In gravida sem non gravida tempor. Nam varius ligula in est volutpat, vel elementum neque convallis. Proin pharetra gravida nunc id dictum. Sed non dictum sem. Curabitur finibus porta aliquet.Nulla facilisi. Proin odio turpis, fermentum quis consectetur ac, cursus condimentum velit. Cras venenatis dolor nec nunc facilisis convallis. Proin id nibh interdum, sollicitudin ipsum vitae, tristique purus. Nunc non odio euismod, tincidunt nisl ac, ultricies risus. Aenean mollis hendrerit aliquam. Nunc tellus metus, maximus nec diam eu, ultrices aliquam tortor. Nunc et felis pretium, porttitor augue in, bibendum ante. Quisque vel bibendum orci, sit amet pharetra dui. Aenean convallis dictum pellentesque. Maecenas lacinia eu libero id cursus. Curabitur eros erat, facilisis id placerat sed, aliquam quis ipsum. Integer pellentesque libero urna, at interdum elit vehicula ut. Suspendisse varius tempus eleifend.Phasellus bibendum maximus orci. Curabitur aliquam sapien quis dolor faucibus, id fringilla risus vestibulum. Nunc egestas dapibus elit, et hendrerit libero tincidunt ut. Nam facilisis sed elit id malesuada. Suspendisse felis eros, dignissim nec pulvinar at, maximus commodo ex. Aenean vulputate ut augue at condimentum. Maecenas finibus rhoncus ante, a dignissim nisl volutpat at. Nullam sit amet sapien vel libero facilisis ornare. Pellentesque semper felis non odio consectetur, et tincidunt leo tincidunt. Sed at luctus diam.", rating: 3, timestamp: Date()))
    }
}

```
