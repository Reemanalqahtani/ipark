Booking.swift
//  CarParkingSwiftUI
//
//  Created by Mona on 19/05/1444 AH.
//

import SwiftUI

struct Booking: View {
    @State var segmants = 0
    var body: some View {
        NavigationView {
            VStack {
                Text("Your Booking")
                    .foregroundColor(.black)
                    .frame(maxWidth: .infinity, maxHeight: 100)
                    .font(.title)
                    .offset(x:1 , y:-190)
                    
                    .foregroundColor(Color("azrg"))
                Picker("", selection: $segmants){
                    Text("Now").tag(0)
                    Text("Past").tag(1)
                       
                    
                    
                }
                .offset(x: 1, y: -190)
                .pickerStyle(SegmentedPickerStyle())
                
                .padding()
                
                .onAppear {
                    UISegmentedControl.appearance().selectedSegmentTintColor = .blue
                    UISegmentedControl.appearance().setTitleTextAttributes([.foregroundColor: UIColor.white], for: .selected)
                    
                    UISegmentedControl.appearance().setTitleTextAttributes([.foregroundColor: UIColor.blue], for: .normal)
                    
                    
                }
                
                if (segmants == 0){
                    NowView()
                  // Payment()
                    
                }else if (segmants == 1){
                    PastView()
                }
                
                
            }
        }
    }
    
    
    
    struct Booking_Previews: PreviewProvider {
        static var previews: some View {
            Booking()
        }
    }
}
