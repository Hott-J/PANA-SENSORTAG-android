# PANA-SENSORTAG-android
-private void checkOad() {
// Check if OAD is supported (needs OAD and Connection Control service)
mOadService = null;
mConnControlService = null;

	for (int i = 0; i < mServiceList.size()
	    && (mOadService == null || mConnControlService == null); i++) {
		BluetoothGattService srv = mServiceList.get(i);
		if (srv.getUuid().equals(GattInfo.OAD_SERVICE_UUID)) {
			mOadService = srv;
		}
		if (srv.getUuid().equals(GattInfo.CC_SERVICE_UUID)) {
			mConnControlService = srv;
		}
	}
}
현재 server list에는 9개의 UUID가 있다. (Log로 출력시켜본 결과)
이 중에 OAD_Service_UUID 는 있지만, .CC_SERVICE_UUID는 존재하지 않는다.
checkOad 함수에서 mConnControlService 값이 항상 null 일 수 밖에 없다.
