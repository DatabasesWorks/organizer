set (organizer_HDRS
	appointment.h
	holiday.h
	daylistmodel.h
	dbmanager.h
	contact.h
	contactmodel.h
	schedulelistmodel.h
	birthdaylistmodel.h
	preferences.h	
	)

set ( organizer_SRCS
	
	main.cpp
	mainwindow.cpp
	
	daylistmodel.cpp
	dbmanager.cpp
	dialogappointment.cpp
	contactmodel.cpp
	proxymodelcontacts.cpp
	dialogcontact.cpp
	dialogabout.cpp
	dialogupcomingschedule.cpp
	dialogupcomingbirthdays.cpp
	schedulelistmodel.cpp
	birthdaylistmodel.cpp
	dialogrepeatappointment.cpp
	dialogappointmentupdate.cpp
	dialogpreferences.cpp	
	)

set (organizer_UIS

mainwindow.ui
	dialogappointment.ui	
	dialogcontact.ui
	dialogabout.ui
	dialogupcomingschedule.ui
	dialogupcomingbirthdays.ui
	dialogrepeatappointment.ui
	dialogappointmentupdate.ui
	dialogpreferences.ui
	)
QT5_WRAP_UI(UIS ${organizer_UIS})

set ( organizer_RSCS
	icons.qrc
	)
QT5_ADD_RESOURCES(RSCS ${organizer_RSCS})

set ( organizer_MOCS
	
	mainwindow.h
	dialogappointment.h
	proxymodelcontacts.h	
	dialogcontact.h
	dialogabout.h
	dialogupcomingschedule.h	
	dialogupcomingbirthdays.h
	dialogrepeatappointment.h	
	dialogappointmentupdate.h
	dialogpreferences.h	
	)
QT5_WRAP_CPP(MOCS ${organizer_MOCS})

add_executable ( organizer ${organizer_SRCS} ${UIS} ${RSCS} ${TRS} ${MOCS} )
target_link_libraries ( organizer  Qt5::Core Qt5::Gui Qt5::Widgets Qt5::Sql Qt5::Svg Qt5::Xml )


INSTALL(TARGETS
    organizer
    RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
    COMPONENT Runtime
)

